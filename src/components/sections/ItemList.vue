<template>
<div>
    <section id="albums" v-if="loaded">
        <Item v-for="(album,index) in albums"
        :key=index
        :img=album.poster
        :title=album.title
        :author=album.author
        :release=album.year
        />
    </section>
    <Loader v-else />
</div>

</template>

<script>
import axios from 'axios';
import Item from '../commons/Item.vue';
import Loader from '../commons/Loader.vue';

export default {
    name: "ItemList",
    components:{
        Item,
        Loader
    },
    data(){
        return{
            apiURL : "https://flynn.boolean.careers/exercises/api/array/music",
            albums : [],
            loaded : false
        }
    },
    methods: {
        getAlbums(){
            axios
                .get(this.apiURL)
                .then((albumList) => {
                    this.albums = albumList.data.response;
                    this.loaded = true;
                })
                .catch(function(error){
                    console.log(error);
                });
        }
    },
    created(){
        this.getAlbums();
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/global.scss";
    #albums{
        display:flex;
        justify-content: space-between;
        flex-wrap: wrap;
        max-width: $container-size;
        margin: 0 auto;
        padding-top: 100px;
    }
</style>