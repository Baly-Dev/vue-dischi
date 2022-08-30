<template>
    <header>
        <div class="left">
            <img class="logo" src="@/assets/spoty_logo.png" alt="">
        </div>
        <div class="right">
            <SongGenereFilter @click="emitChoiceGenre" :genres="genres" @emitGenre="getChoiceGenre"/>
        </div>
    </header>
</template>

<script>
import SongGenereFilter from '@/components/SongGenereFilter.vue'
export default{
    name: 'AppHeader',
    props:{
        genres: Array
    },
    data(){
        return{
            genre: null
        }
    },
    methods:{
        getChoiceGenre: function(genre){
            this.genre = genre
            this.emitChoiceGenre()
        },
        emitChoiceGenre: function(){
            this.$emit('emitGenre', this.genre)
        }
    },
    components:{
        SongGenereFilter
    }
}
</script>

<style lang="scss">
@import '@/styles/global.scss';

header{
    background-color: $primary-dark;
    padding: 0px 30px;
    height: 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    .logo{
        width: 140px;
    }
}
</style>