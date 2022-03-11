<template>
    <div class="container">
        <div class="select-wrapper">
            <select 
            v-model="parametro" 
            @change="$emit('selectedgenre', parametro)" 
            name="genre" id="genre">
                <option value="">Scegli il tuo genere preferito</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
            <span class="custom-arrow"></span>
        </div>
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

    select{
        font-size: 16px;
        appearance: none;
        padding: 10px 60px 10px 20px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        background-color: rgba(255, 255, 255, 0.11);
        color: rgba(255, 255, 255, 0.5);
        box-shadow: inset 0px 1px 4px 0px rgb(255 255 255 / 29%);

        &:hover{
            background-color: rgba(255, 255, 255, 0.288);
            color: rgb(255, 255, 255);
            transition: all 500ms;
        }
    }

    option{
        color: rgba(255, 255, 255, 0.5);
        background-color: #374451;
    }

    .select-wrapper{
        position: relative;
        display: inline-block;
    }

    .custom-arrow{
        position: absolute;
        right: 0;
        top: 0;
        display: block;
        background: linear-gradient(90deg, rgba(255,255,255,0) 0%, rgba(255,255,255,0.21752450980392157) 43%, rgba(255, 255, 255, 0.432) 100%);
        width: 50px;
        height: 100%;
        border-radius: 0 10px 10px 0;
        pointer-events: none;
    }

    .custom-arrow:after{
        content: '';
        position: absolute;
        top: 50%;
        left: 55%;
        transform: translate(-50%, -50%);
        border-top: 6px solid #374451;
        border-left: 6px solid transparent;
        border-right: 6px solid transparent;

    }

</style>