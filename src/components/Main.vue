<template>
 <div>
    <div v-if="Loader == false" class="d-flex flex-wrap">
      <Albums v-for="(album,index) in genresHeaderFilter" :key="index" :prod="album"/>
    </div>
    <Loader v-else/>
 </div>

</template>

<script>
const axios = require('axios');
import Albums from "./Albums.vue";
import Loader from "./Loader.vue";
export default {
  name: 'Main',
   components : {
        Albums,
        Loader
    },
    props:["filterGenre"],
  data() {
    return{
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
      AlbumsLink:[],
      Loader: true,
    }
  },
  created() {
    this.albumList();
  },
  computed: {
    genresHeaderFilter() {
      return this.AlbumsLink.filter((el)=>{
        if(){
        return el.genre.includes(this.filterGenre)
        }
      })
    }
  },
  methods: {
    albumList() {
     axios.get(this.APIUrl)
      .then(el => {
        console.log(el.data.response)
        this.AlbumsLink = el.data.response;
      })
      setTimeout(() => {this.Loader = false;},3000)
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">


</style>
