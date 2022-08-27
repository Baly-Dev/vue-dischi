<template>
    <header>
        <div class="left">
            <img class="logo" src="@/assets/spoty_logo.png" alt="">
        </div>
    </header>
</template>

<script>
export default{
    name: 'AppHeader'
}
</script>

<style lang="scss">

@import '@/styles/global.scss';

header{
    background-color: $primary-dark;
    padding: 0px 30px;
    height: 80px;
    display: flex;
    align-items: center;

    .logo{
        width: 140px;
    }
}

</style>