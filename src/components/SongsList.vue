<template>
    <div class="card-group">
        <SongCard v-for="(song, i) in songs" :key="i" :song="song"/>
    </div>
</template>

<script>
import SongCard from './SongCard.vue'
export default {
    name: "SongsList",
    props:{
        songs: Array
    },
    components: { 
        SongCard 
    }
}
</script>

<style scoped lang="scss">
.card-group{
    display: flex;
    flex-wrap: wrap;

    .card{
        width: calc((100% / 5) - 15px);
        margin-bottom: 15px;
        margin-right: 10px;
    }
}
</style>