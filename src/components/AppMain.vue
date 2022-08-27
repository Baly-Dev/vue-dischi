<template>
    <section>
        <div class="container">
            <SongsList />
        </div>
    </section>
</template>

<script>
import SongsList from './SongsList.vue';
export default {
    name: "AppMain",
    components: { SongsList }
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