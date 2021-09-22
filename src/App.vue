<template>
<div>
  <Header/>
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
  }
}
</script>

<style lang="scss">
@import "@/style/Utilitis";
</style>
