<template>
    <main>
        <ItemList />
    </main>
</template>

<script>
import ItemList from '../sections/ItemList.vue'


export default {
    name: "Main",
    components:{
        ItemList
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/global.scss";
    main{
        background-color: $main-background;
        height: calc(100vh - 60px);
    }
</style>