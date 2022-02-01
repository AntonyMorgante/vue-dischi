<template>
  <section class="loading-screen">
      <p class="loading-text">Caricamento...</p>
  </section>
</template>

<script>
export default {
    name: "Loader"
}
</script>

<style lang="scss" scoped>
@import "../../assets/global.scss";

    .loading-screen{
        position:fixed;
        top:0;
        left:0;
        width: 100vw;
        height: 100vh;
        z-index: 99;
        background-color: $item-background;
    }

    .loading-text{
        color:white;
        text-align: center;
        font-size: 30px;
        text-transform: uppercase;
        padding-top: calc(50vh - 30px);
    }
</style>