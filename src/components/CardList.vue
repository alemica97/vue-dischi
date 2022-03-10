<template>
    <main>
        <div class="container">

        </div>
    </main>
</template>

<script>
import axios from 'axios'

export default {
    name: 'cardList',
    data(){
        return{
            // success: true,
            playerCards: [],
        }
    },

    methods: {
        fetchCards : function(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(res => {
                // this.success = res.data.success;
                this.playerCards = res.data.response;
                console.log(this.playerCards);
            })
        }
    },

    created(){
        this.fetchCards();
    },
}
</script>

<style lang="scss" scoped>

</style>