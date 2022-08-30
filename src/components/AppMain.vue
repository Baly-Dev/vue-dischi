<template >
    <section>
        <div class="container">
            <SongsList :songs="filtredGenres"/>
        </div>
    </section>
</template>

<script>
import axios from 'axios'
import SongsList from './SongsList.vue';
export default {
    name: "AppMain",
    props:{
        genre: String
    },
    data(){
        return{
            songs: [],
            genres: [],
            endpoint: "https://flynn.boolean.careers/exercises/api/array/music",
        }
    },
    created(){
        this.apiCall()
    },
    methods:{
        apiCall: function () {
            axios.get(this.endpoint).then(response => {
                this.songs = response.data.response;
                this.setEmitSongs()
            })
                .catch(err => {
                console.log(err);
            });
        },
        setEmitSongs: function(){
            this.getSongsGeneres()
            this.$emit('emitSongs', this.genres)
        },
        getSongsGeneres: function(){
            if (this.songs.length > 0){
                this.songs.forEach(song => {
                    if (!this.genres.includes(song.genre)){
                        this.genres.push(song.genre)
                    }
                })
                return this.genres
            }
        }
    },
    computed:{
        filtredGenres: function(){
            if (this.genre == null){
                return this.songs
            }else{
                const filtredSongs = this.songs.filter(song => {
                    if(song.genre.includes(this.genre)){
                        return true
                    }else{
                        return false
                    }
                })
                return filtredSongs
            }
        }
    },
    components: { 
        SongsList 
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/global.scss';

section{
    background-color: $primary-light;
    height: calc(100vh - 80px);
    display: flex;
    align-items: center;
}
</style>