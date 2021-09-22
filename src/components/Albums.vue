<template>
  <div>
      <img :src="prod.poster" alt="">
      <h1>{{prod.title}}</h1>
      <h3>{{prod.author}}</h3>
      <h4>{{prod.year}}</h4>
  </div>
</template>

<script>
export default {
    props : ["prod"]
}
</script>

<style>

</style>