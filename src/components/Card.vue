<template>
    <main>
        <div class="player-card">
            <figure class="card-image">
                <img :src="player.poster">
            </figure>
            <div class="card-title">
                <h2>{{ player.title }}</h2>
            </div>
            <div class="card-info">
                <span>{{ player.author }}</span>
                <span>{{ player.year }}</span>
            </div>
        </div>
    </main>
</template>

<script>
export default {
    name: 'myCard',

    props: {
        player: {
            type: Object,
            require: true,
        }
    },
    created(){
        console.log(this.props)
    }
}
</script>

<style lang="scss" scoped>

</style>