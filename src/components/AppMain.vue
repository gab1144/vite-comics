<script>
  import BlueBar from './BlueBar.vue'
  export default {
    name: 'AppMain',
    components: {
      BlueBar
    }
  }
</script>

<template>
  <main>
    <div class="container">
      <h2> ---&gt; Content goes here &lt;--- </h2>
    </div>

    <BlueBar/>
    
  </main>
</template>


<style lang="scss" scoped>
  main {
    background-color: black;
    color: white;
    .container{
      padding: 50px 0;
    }
  }
</style>