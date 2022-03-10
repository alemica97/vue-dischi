<template>
    <main>
        <div class="container">
            <myCard 
            class="player-wrapper"
            v-for="(player, i) in playerCards" 
            :key="i" 
            :player="player"/>
        </div>
    </main>
</template>

<script>
import axios from 'axios'
import myCard from './Card.vue'

export default {
    name: 'cardList',

    components: {
        myCard,
    },

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

    .container{
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
    }

    .player-wrapper{
        width: calc(100% / 5);
    }
</style>