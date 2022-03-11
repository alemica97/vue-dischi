<template>
    <main>
        <selectGenre @selectegenre="" />
        <cardList />
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
            // genreSelected: '',
        }
    },
    // computed: {

    // }
}
</script>

<style lang="scss" scoped>
    main{
        height: 100vh;
        background-color: #1E2D3B;
    }
</style>