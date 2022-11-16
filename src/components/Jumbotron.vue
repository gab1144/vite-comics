<script>
export default {
  name: 'Jumbotron'
}
</script>


<template>
  <div class="jumbotron">
  </div>
</template>


<style lang="scss" scoped>
  @use '../style/partials/variables' as *;
  .jumbotron {
    background-image: url('../assets/img/jumbotron.jpg');
    background-size: cover;
    height: 400px;
  }
</style>