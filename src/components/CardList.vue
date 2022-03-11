<template>
    <main>
        <div v-if="playerCards.length < 10" class="loader">
            <list-loader />
        </div>
        <div v-else class="container">
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
import listLoader from './Loader.vue'

export default {
    name: 'cardList',

    components: {
        myCard,
        listLoader,
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
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        gap: 40px;
        padding: 80px 0;
        position: relative;
    }

    .player-wrapper{
        width: calc((100% - 160px) / 5);
    }

    .loader{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
</style>