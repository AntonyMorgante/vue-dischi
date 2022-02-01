<template>
<div>
    <select 
    name="filter-bar" 
    id="filter-bar" 
    v-model="genreSelected" 
    @change="$emit(`filterAlbums`,genreSelected)"
    >
      <option value="All">Tutti i generi</option>
      <option value="Pop">Pop</option>
      <option value="Rock">Rock</option>
      <option value="Metal">Metal</option>
      <option value="Jazz">Jazz</option>
  </select>
</div>
</template>

<script>
export default {
    name:"FilterGenre",
    data(){
        return{
            genreSelected : "All"
        }
    },
    methods:{
        filterAlbums: function(){
             console.log("genreSelected")
        }
    }
}
</script>

<style>
    select{
        width: 190px;
        padding:3px;
        text-align: center;
        margin-bottom:30px;
    }
</style>