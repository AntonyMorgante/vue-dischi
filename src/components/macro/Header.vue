<template>
    <header>
        <img class="logo" src="../../assets/logo.svg" alt="">
    </header>
</template>

<script>


export default {
    name: "Header"
}
</script>

<style lang="scss" scoped>
@import "../../assets/global.scss";
    header{
        height: 60px;
        background-color: $item-background;
    }

    .logo{
        height: 40px;
        padding-top: 10px;
        margin-left: 30px;
    }
</style>
