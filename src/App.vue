<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from './components/macro/Header.vue'
import Main from './components/macro/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
  @import "./assets/global.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body{
  margin:0;
  padding: 0;
  box-sizing: border-box;
}
</style>
