<script>
  export default {
    name: 'BlueBar',
  data(){
    return{
      icons: [
        {
          img: "buy-comics-digital-comics.png",
          text: "Digital Comics"
        },
        {
          img: "buy-comics-merchandise.png",
          text: "DC merchandise"
        },
        {
          img: "buy-comics-subscriptions.png",
          text: "subscriptions"
        },
        {
          img: "buy-comics-shop-locator.png",
          text: "Comic shop locator"
        },
        {
          img: "buy-dc-power-visa.svg",
          text: "power visa"
        }
      ]
    }
  },
  methods:{
    getImagePath(imageName){
      return new URL(`../assets/img/${imageName}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <section class="icons-area">
    <div class="container">
      <div class="icon"
        v-for="icon of icons">
          <img :src="getImagePath(icon.img)" alt="">
          <span>{{icon.text}}</span>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
  @use '../style/partials/variables' as *;
  @use '../style/partials/mixin' as *;

  .icons-area {
    background-color: $primary-color;
    .container {
      @include centerFlex('both');
      flex-wrap: wrap;
      text-transform: uppercase;
      .icon {
        padding: 50px 0;
        width: calc(100%/5);
        min-width: 205px;
        @include centerFlex('both');
        img {
          height: 55px;
          margin-right: 15px;
        }
        span {
          display: block;
          text-overflow: ellipsis;;
        }
      }
    }
  }
</style>