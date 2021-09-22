<template>
  <div class="albums">
      <img :src="prod.poster" alt="">
      <div>
        <!-- <h1>{{prod.title}}</h1>
        <h3>{{prod.author}}</h3>
        <h4>{{prod.year}}</h4> -->
      </div>
  </div>
</template>

<script>
export default {
    props : ["prod"]
}
</script>

<style scoped lang="scss">
@import "@/style/Albums";
</style>