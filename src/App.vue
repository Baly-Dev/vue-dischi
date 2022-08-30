<template>
  <div id="app">
    <AppHeader :genres="genres" @emitGenre="getGenre" />
    <AppMain @emitSongs="getGenres" :genre="genre"/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  data(){
    return{
      genres: [],
      genre: null
    }
  },
  components: {
    AppHeader,
    AppMain
  },
  methods:{
    getGenres: function(genres){
      this.genres = genres
    },
    getGenre: function(genre){
      this.genre = genre
      console.log(this.genre)
    }
  }
}
</script>

<style lang="scss">

@import './styles/global.scss';

</style>
