<template>
    <main>
        <cardList />
    </main>
</template>

<script>
import cardList from './CardList.vue'

export default {
    name: 'myMain',

    components:{
        cardList,
    }
}
</script>

<style lang="scss" scoped>
    main{
        height: 100vh;
        background-color: #1E2D3B;
    }
</style>