<template>
<div class="card">
    <div class="card-header">
        <img :src="song.poster" alt="">
    </div>
    <div class="card-body">
        <h3 class="song-title"> {{song.title}}</h3>
        <small class="song-author"> {{song.author}} </small>
        <small class="song-year"> {{song.year}} </small>
    </div>
</div>
</template>

<script>
export default {
    name: 'SongCard',
    props: {
        song: Object
    }
}
</script>

<style scoped lang="scss">

@import '@/styles/global.scss';

.card{
    padding: 20px;
    background-color: $primary-dark;
    text-align: center;
    color: #fff;

    img{
        width: 100%;
        height: 200px;
        margin-bottom: 15px;
    }

    h3{
        margin-bottom: 15px;
        text-transform: uppercase;
    }

    small{
        display: block;
        margin-bottom: 5px;
        color: rgb(142, 142, 142);
    }
}
</style>