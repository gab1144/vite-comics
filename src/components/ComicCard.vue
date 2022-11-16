<script>
export default {
  name: 'ComicCard',
  props:{
    cardImage: String,
    cardTitle: String,
    comicPrice: String,
  },
  data(){
    return{ 
      isHover: false
    }
  }
}
</script>


<template>
  <div class="card"
  @mouseover="isHover = true"
  @mouseleave="isHover = false">
    <div class="img-area">
      
      <img :src="cardImage" :alt="cardTitle">

      <div class="price-hover" v-if="isHover">
        <span>{{comicPrice}}</span>
      </div>

    </div>
    <span>{{cardTitle}}</span>
  </div>
</template>


<style lang="scss" scoped>
  @use '../style/partials/variables' as *;
  @use '../style/partials/mixin' as *;
  
  .card{
    margin-bottom: 45px;
    padding: 0 12.5px;
    width: calc(100% / 6);
    min-width: 190px;
    text-transform: uppercase;
    &:hover {
      cursor: pointer;
    }
    &:hover img{
      opacity: 0.5;
    }
    .img-area {
      width: 100%;
      aspect-ratio: 1;
      overflow: hidden;
      margin-bottom: 20px;
      position: relative;
    }

    .price-hover{
      position: absolute;
      z-index: 999;
      top: 0;
      left: 0;
      width: 100%;
      aspect-ratio: 1;
      @include centerFlex('both');
      span {
        display: block;
      }
    }
  }
</style>