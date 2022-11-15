<script>
  export default {
    name: 'AppHeader',
    data(){
    return{
      menu:[
        {
          text: 'Characters',
          href: '#',
          current: false
        },
        {
          text: 'Comics',
          href: '#',
          current: true
        },
        {
          text: 'Movies',
          href: '#',
          current: false
        },
        {
          text: 'Tv',
          href: '#',
          current: false
        },
        {
          text: 'Games',
          href: '#',
          current: false
        },
        {
          text: 'Collectibles',
          href: '#',
          current: false
        },
        {
          text: 'Videos',
          href: '#',
          current: false
        },
        {
          text: 'Fans',
          href: '#',
          current: false
        },
        {
          text: 'News',
          href: '#',
          current: false
        },
        {
          text: 'Shop',
          href: '#',
          current: false
        }
      ]
    }
  }
  }
</script>

<template>
  <header class="container">
  <div class="logo">
    <!-- percorso assoluto perché l'immagine è in public -->
    <img src="/dc-logo.png" alt="Logo Dc">
  </div>
  
  <nav>
      <ul>
        <li
          v-for="(link, index) in menu"
          :key="index"
        ><a :class="{'active': link.current}" :href="link.href">{{link.text}}</a></li>
      </ul>
    </nav>
  
  </header>
</template>

<style lang="scss" scoped>

  @use '../style/partials/variables' as *;
  @use '../style/partials/mixin' as *;

  header {
    display: flex;
    justify-content: space-between;
    height: 115px;
    .logo {
      @include centerFlex('vertical');
      
      img {
        height: 80%;
      }
    }
    ul {
      list-style: none;
      display: flex;
      height: 100%;
      text-transform: uppercase;
      
      li{
        height: 100%;
        @include centerFlex('vertical');
        padding-top: 30px;
      }

      a {
        height: 100%;
        text-decoration: none;
        display: inline-block;
        padding: 1rem;
        color: black;
        font-weight: 600;
          &:hover,
          &.active{
          border-bottom: 6px solid $primary-color;
          }
      }
    }
  }
</style>