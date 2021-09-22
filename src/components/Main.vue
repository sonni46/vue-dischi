<template>
 <div class="d-flex">
   <Albums v-for="(album,index) in AlbumsLink" :key="index" :prod="album"/>
 </div>
</template>

<script>
const axios = require('axios');
import Albums from "./Albums.vue"
export default {
  name: 'Main',
   components : {
        Albums
    },
  data() {
    return{
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
      AlbumsLink:[],
    }
  },
  created() {
    this.albumList();
  },
  methods: {
    albumList() {
     axios.get(this.APIUrl)
      .then(el => {
        console.log(el.data.response)
        this.AlbumsLink = el.data.response
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
