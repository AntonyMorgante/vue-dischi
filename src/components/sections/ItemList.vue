<template>
<div>
    <section id="albums" v-if="loaded">
        <FilterGenre @filterAlbums="filterCatalog" />
        <div class="album-catalog">
            <Item v-for="(album,index) in filteredCatalog"
            :key=index
            :img=album.poster
            :title=album.title
            :author=album.author
            :release=album.year
            />
        </div>
    </section>
    <Loader v-else />
</div>

</template>

<script>
import axios from 'axios';
import Item from '../commons/Item.vue';
import Loader from '../commons/Loader.vue';
import FilterGenre from '../commons/FilterGenre.vue';

export default {
    name: "ItemList",
    components:{
        Item,
        Loader,
        FilterGenre
    },
    data(){
        return{
            apiURL : "https://flynn.boolean.careers/exercises/api/array/music",
            albums : [],
            albumsReplica: [],
            loaded : false,
            genre: "All"
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
        },
        filterCatalog: function (genreSelected) {
            this.genre = genreSelected;
        }
    },
    created(){
        this.getAlbums();
    },
    computed: {
        filteredCatalog(){
            if (this.genre == "All"){
                return this.albums;
            } else {
                return this.albums.filter( (album) => {
                    return album.genre == this.genre; 
                }
            )}
        }
    }
}
    

</script>

<style lang="scss" scoped>
@import "../../assets/global.scss";
    #albums{
        max-width: $container-size;
        margin: 0 auto;
        padding-top: 60px;
        text-align: center;

        .album-catalog{
            display:flex;
            justify-content: center;
            flex-wrap: wrap;
        }
    }
</style>