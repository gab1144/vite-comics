<script>
  import Jumbotron from './Jumbotron.vue';
  import ComicCard from './ComicCard.vue';
  import BlueBar from './BlueBar.vue';
  import comics from '../data/dc-comics';

  export default {
    name: 'AppMain',
    components: {
      BlueBar,
      ComicCard,
      Jumbotron
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
      <div class="card-area">
        <ComicCard
        v-for="(comic, index) of comics" 
        :key="index"
        :cardImage="comic.thumb"
        :cardTitle="comic.series"/>
      </div>
    </div>

    <BlueBar/>
    
  </main>
</template>


<style lang="scss" scoped>
  main {
    background-color: black;
    color: white;
    .container {
      padding: 50px 0;
    }

    .card-area {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      width: 100%;
    }
  }
</style>