<template>
<div class="container-app black">
  <Header @valueGenres="valueHeader" :filterGenre="value" />
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
  data (){
    return {
      value :"all",
    }
  },
  created() {
    this.valueHeader()
  },
  methods : {
  valueHeader(info) {
    this.value = info
  }

  }
}
</script>

<style lang="scss">
@import "@/style/Utilitis";
</style>
