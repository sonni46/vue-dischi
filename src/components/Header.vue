<template>
  <div class="logo">
    <img src="https://images-na.ssl-images-amazon.com/images/I/41xu2Bdb4oL.jpg" alt="">
    <div>
      <select v-model="info" @change="$emit('valueGenres',info)" name="" id="">
        <option value="all">All</option>
        <option v-for="(genre,index) in genreList" :key="index" :value="genre.genre">{{genre.genre}}</option>
      </select>
    </div>
  </div>
</template>

<script>
const axios = require('axios');
export default {
    name : "Header",
    data () {
      return {
        genreList: [],
        genreListFilter: [],
        info:"all",
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
    //    genresFilter () {
    //    return this.genreList.filter(element => {
    //     if(this.genreListFilter.includes(element.genre)) {
    //        return this.genreListFilter.push(element.genre);
    //     }
    //   });
    // }
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