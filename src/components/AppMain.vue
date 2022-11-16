<script>
  import Jumbotron from './Jumbotron.vue';
  import ComicCard from './ComicCard.vue';
  import ButtonLoadMore from './ButtonLoadMore.vue';
  import BlueBar from './BlueBar.vue';
  import comics from '../data/dc-comics';

  export default {
    name: 'AppMain',
    components: {
      BlueBar,
      ComicCard,
      Jumbotron,
      ButtonLoadMore
    },
    data(){
      return{
        comics
      }
    }
  }
</script>

<template>
  <main>
    <Jumbotron/>
    <div class="container">
      <span class="tag">Current series</span>

      <div class="card-area">
        <ComicCard
        v-for="(comic, index) of comics" 
        :key="index"
        :cardImage="comic.thumb"
        :cardTitle="comic.series"
        :comicPrice="comic.price"/>
      </div>

      <ButtonLoadMore/>

    </div>

    <BlueBar/>
    
  </main>
</template>


<style lang="scss" scoped>
@use '../style/partials/variables' as *;
  main {
    background-color: black;
    color: white;
    .container {
      padding: 50px 0;
      position: relative;
      display: flex;
      flex-direction: column;
      .tag {
        text-transform: uppercase;
        position: absolute;
        top: calc(-15px - 12.5px);
        left: 0;
        background-color: $primary-color;
        padding: 15px 30px;
        font-size: 25px;
        font-weight: 800;
      }
      .btn-load-more {
        align-self: center;
      }
    }
    
    .card-area {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      width: 100%;
    }
  }
</style>