<template>
    <section id="albums">
        <Item v-for="(album,index) in albums"
        :key=index
        :img=album.poster
        :title=album.title
        :author=album.author
        :release=album.year
        />
    </section>
</template>

<script>
import axios from 'axios';
import Item from '../commons/Item.vue';

export default {
    name: "ItemList",
    components:{
        Item
    },
    data(){
        return{
            apiURL : "https://flynn.boolean.careers/exercises/api/array/music",
            albums : []
        }
    },
    methods: {
        getAlbums(){
            axios
                .get(this.apiURL)
                .then((albumList) => {
                    this.albums = albumList.data.response;
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