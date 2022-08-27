<template>
    <div class="card-group">
        <SongCard v-for="(song, i) in songs.response" :key="i" :song="song"/>
    </div>
</template>

<script>
import axios from 'axios'
import SongCard from './SongCard.vue'
export default {
    name: "SongsList",
    data() {
        return {
            songs: [],
            endpoint: "https://flynn.boolean.careers/exercises/api/array/music"
        };
    },
    mounted() {
        this.apiCall();
    },
    methods: {
        apiCall: function () {
            axios.get(this.endpoint).then(response => {
                this.songs = response.data;
                console.log(this.songs.response);
            })
                .catch(err => {
                console.log(err);
            });
        }
    },
    components: { SongCard }
}
</script>

<style scoped lang="scss">
.card-group{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    .card{
        width: calc((100% / 5) - 15px);
        margin-bottom: 15px;
    }
}
</style>