<template>
    <div class="container">
        <select 
        v-model="parametro" 
        @change="$emit('selectedgenre', parametro)" 
        name="genre" id="genre">
            <option value="">Scegli il tuo genere preferito</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
        </select>
        <!-- <h1>{{ parametro }}</h1> -->
    </div>
</template>

<script>
export default {
    name: 'selectGenre',

    data(){
        return{
            parametro: '',
        }
    }
}
</script>

<style lang="scss" scoped>
    .container{
        text-align: center;
        padding: 80px 0 0 0;
    }
</style>