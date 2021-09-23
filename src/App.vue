<template>
<div class="container-app black">
  <Header @valueSelect="valueHeader" :filterGenre="value" />
  <div class="container">
    <Main/>
  </div>
</div>
</template>

<script>
import Main from '@/components/Main.vue'
import Header from '@/components/Header.vue'
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return {
      value :"All",
    }
  },
  created() {
    this.valueHeader()
  },
  methods : {
  valueHeader(info) {
    // console.log(info)
    this.value = info
  }

  }
}
</script>

<style lang="scss">
@import "@/style/Utilitis";
</style>
