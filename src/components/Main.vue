<template>
    <main>
        <div class="container">
            <cardList />
        </div>
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

</style>