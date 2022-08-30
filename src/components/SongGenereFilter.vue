<template>
<form>
    <select class="form-select"  v-model="slectedGenre" @change="emitChoiceGenre">
        <option value="Genres" selected disabled hidden>Genres</option>
        <option v-for="(genre, i) in genres" :value="genre" :key="i" >{{genre}}</option>
    </select>
</form>
</template>

<script>
export default {
    name: 'SongGenereFilter',
    props:{
        genres: Array
    },
    data(){
        return {
            slectedGenre: 'Genres'
        }
    },
    methods:{
        emitChoiceGenre: function(){
            this.$emit('emitGenre', this.slectedGenre)
        }
    }
}
</script>

<style scoped lang="scss">
    @import '@/styles/global.scss';

    select {
        background-color: $btn-dark;
        border: 3px solid $btn-dark;
        border-radius: 6px;
        line-height: 1.5em;
        padding: 0.5em 3.5em 0.5em 1em;
        font-size: 1.1rem;
        color: #fff;

        margin: 0;      
        box-sizing: border-box;
        -webkit-appearance: none;
        }

        option{
            color: #fff;
        }

    select.form-select {
        background-image:
            linear-gradient(45deg, transparent 50%, #fff 50%),
            linear-gradient(135deg, #fff 50%, transparent 50%),
            linear-gradient(to right, #fff, #fff);
        background-position:
            calc(100% - 20px) calc(1em + 2px),
            calc(100% - 15px) calc(1em + 2px),
            calc(100% - 2.5em) 0.5em;
        background-size:
            5px 5px,
            5px 5px,
            1px 1.5em;
        background-repeat: no-repeat;

        &:focus {
            background-image:
                linear-gradient(45deg, #fff 50%, transparent 50%),
                linear-gradient(135deg, transparent 50%, #fff 50%),
                linear-gradient(to right, #fff, #fff);
            background-position:
                calc(100% - 15px) 1em,
                calc(100% - 20px) 1em,
                calc(100% - 2.5em) 0.5em;
            background-size:
                5px 5px,
                5px 5px,
                1px 1.5em;
            background-repeat: no-repeat;
            border-color: $primary-light;
            outline: 0;
        }
    }
</style>