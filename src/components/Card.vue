<template>
    <main>
        <div class="player-card">
            <figure class="card-image">
                <img :src="player.poster">
            </figure>
            <div class="card-title">
                <h3>{{ player.title }}</h3>
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

    .player-card{
        padding: 20px;
        background-color: rgba(255, 255, 255, 0.151);
        text-align: center;
        height: 360px;
    }

    .card-image{
        width: 100%;
        margin-bottom: 15px;
        

        & img{
            aspect-ratio: 1/1;
            object-fit: cover;
            object-position: center;
        }
    }

    .card-title{
        font-size: 20px;
        color: white;
        text-transform: uppercase;
        font-weight: 500;
    }

    .card-info{
        display: flex;
        flex-direction: column;
        gap: 5px;
        color: rgba(255, 255, 255, 0.5);
        font-size: 15px;
        margin-top: 15px;
    }
</style>