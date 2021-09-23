<template>
  <div class="logo">
    <img src="https://images-na.ssl-images-amazon.com/images/I/41xu2Bdb4oL.jpg" alt="">
    <div>
      <select v-model="info" @change="$emit('valueSelect',info)" name="" id="">
        <option value="All">All</option>
        <option v-for="(genre,index) in genresFilter" :key="index" :value="genre" >{{genre}}</option>
      </select>
    </div>
  </div>
</template>

<script>
const axios = require('axios');
export default {
    name : "Header",
    data() {
      return {
        genreList: [],
        info:"All",
      }
    },
    created() {
      this.genres();
      this.genresFilter();
    },
    methods: {
      genres() {
     axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then(el => {
            this.genreList = el.data.response;
      })
    },
  },
    computed : {
      genresFilter() {
        const filterGen=[];
        this.genreList.forEach((album)=>{
        if(filterGen.includes(album.genre) == false){
          filterGen.push(album.genre);
        }
      })
      return filterGen;
    },
       
    }
}
</script>

<style scoped lang="scss">
.logo {
  background-color:#181413 ;
    img {
      width: 4%;
    }
}
</style>