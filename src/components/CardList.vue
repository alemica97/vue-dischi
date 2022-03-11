<template>
    <div class="main-content">
        <div v-if="playerCards.length < 10" class="loader">
            <list-loader />
        </div>
        <div v-else class="container">
            <myCard 
            class="player-wrapper"
            v-for="(playerEl, i) in playerCardsGenreFiltered" 
            :key="i" 
            :player="playerEl"/> <!--  il v-bind della props (player) = "l'elemento dell'array ciclato" -->
        </div>
    </div>
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
    //a questa props passo il valore del data() genreSelected che si trova nel main
    props: {
        genreProps: {
            type: String,
            default: '',
        }
    },

    data(){
        return{
            // success: true,
            playerCards: [],
        }
    },

    computed: {
        // questa funzione ritorna un array con le card che hanno il genere selezionato 
        playerCardsGenreFiltered: function(){
            return this.playerCards.filter((el) => {
                if(el.genre.includes(this.genreProps)){ //uso includes altrimenti se non seleziono un genere, non mostra nessuna card
                    console.log(el.genre);
                    console.log(this.genreProps);
                    return true;
                }else{
                    return false;
                }
            });
        }
    },

    methods: {
        fetchCards : function(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(res => {
                // this.success = res.data.success;
                this.playerCards = res.data.response;
                console.log(this.playerCards);
            });
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