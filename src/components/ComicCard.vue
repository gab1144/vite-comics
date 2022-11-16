<script>
export default {
  name: 'ComicCard',
  props:{
    cardImage: String,
    cardTitle: String
  }
}
</script>


<template>
  <div class="card">
    <div class="img-area">
      <img :src="cardImage" :alt="cardTitle">
    </div>
    <span>{{cardTitle}}</span>
  </div>
</template>


<style lang="scss" scoped>
  @use '../style/partials/variables' as *;
  .card{
    margin-bottom: 45px;
    padding: 0 12.5px;
    width: calc(100% / 6);
    min-width: 190px;
    text-transform: uppercase;
    .img-area {
      width: 100%;
      aspect-ratio: 1;
      overflow: hidden;
      margin-bottom: 20px;
    }

  }
</style>