<template>
  <div class="albums">
    <div class="album">
      <img :src="prod.poster" alt="">
      <div class="info">
        <h2>{{prod.title}}</h2>
        <h3>{{prod.author}}</h3>
        <h4>{{prod.year}}</h4>
      </div>
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