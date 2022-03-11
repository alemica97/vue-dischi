<template>
    <main>
        <!-- ascolto l'evento scatenato dall' $emit nel componente (SelectGenre) -->
        <selectGenre @selectedgenre="getSelectedGenre" />
        <cardList :genreProps="genreSelected" />
    </main>
</template>

<script>
import cardList from './CardList.vue'
import selectGenre from './SelectGenre.vue'

export default {
    name: 'myMain',

    components:{
        cardList,
        selectGenre,
    },

    data(){
        return{
            // questo rimarra un valore non definito finche il valore della select non cambia scatenando un evento 
            genreSelected: '',
        }
    },
    methods: {
        // questo metodo da il valore del parametro portato dalla $emit al data() genreSelected 
        getSelectedGenre: function( genre ){
            // console.log(genre);
            // console.log(this.genreSelected);
            this.genreSelected = genre;
            // console.log(this.genreSelected);
        }
    },
}
</script>

<style lang="scss" scoped>
    main{
        height: 100vh;
        background-color: #1E2D3B;
    }
</style>