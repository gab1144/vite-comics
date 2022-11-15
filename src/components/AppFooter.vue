<script>
  export default {
    name: 'AppFooter',
    data(){
      return{
        footerImg: 'footer.jpg',
        links: [
          {
            linkListName: "Dc comics",
            linkList: [
              {
                text: "Characters",
                href: '#'
              },
              {
                text: "Comics",
                href: '#'
              },
              {
                text: "Movies",
                href: '#'
              },
              {
                text: "TV",
                href: '#'
              },
              {
                text: "Games",
                href: '#'
              },
              {
                text: "Videos",
                href: '#'
              },
              {
                text: "News",
                href: '#'
              }
            ]
          },
          {
            linkListName: "Shop",
            linkList: [
              {
                text: "Shop Dc",
                href: '#'
              },
              {
                text: "Shop Dc Collectibles",
                href: '#'
              }
            ]
          },
          {
            linkListName: "Dc",
            linkList: [
              {
                text: "Terms Of Use",
                href: '#'
              },
              {
                text: "Privacy policy(New)",
                href: '#'
              },
              {
                text: "Ad Choices",
                href: '#'
              },
              {
                text: "Advertising",
                href: '#'
              },
              {
                text: "Jobs",
                href: '#'
              },
              {
                text: "Subscriptions",
                href: '#'
              },
              {
                text: "Talent Workshops",
                href: '#'
              }
              ,
              {
                text: "CPSC Certificates",
                href: '#'
              },
              {
                text: "Ratings",
                href: '#'
              },
              {
                text: "Shop Help",
                href: '#'
              },
              {
                text: "Contact Us",
                href: '#'
              }
            ]
          },
          {
            linkListName: "Sites",
            linkList: [
              {
                text: "Dc",
                href: '#'
              },
              {
                text: "MAD Magazine",
                href: '#'
              },
              {
                text: "DC Kids",
                href: '#'
              },
              {
                text: "Dc Universe",
                href: '#'
              },
              {
                text: "Dc Power Visa",
                href: '#'
              }
            ]
          }
        ],

        socialLinks: [
          {
            img: "footer-facebook.png",
            href: "#"

          },
          {
            img: "footer-twitter.png",
            href: "#"
            
          },
          {
            img: "footer-youtube.png",
            href: "#"
          },
          {
            img: "footer-pinterest.png",
            href: "#"
          },
          {
            img: "footer-periscope.png",
            href: "#"
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
  <footer>
    <div class="footer-top">
      <div class="container">
        <div class="link-area">
          <div class="links"
          v-for="list in links">
            <h4>{{list.linkListName}}</h4>
            <nav>
              <ul>
                <li 
                v-for="link in list.linkList"><a :href="link.href">{{link.text}}</a></li>
              </ul>
            </nav>
          </div>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <div class="container">

        <div class="button">
          <a href="#">Sign-up now!</a>
        </div>
        
        <div class="social-links">
          <h4>Follow us</h4>
          <ul>
            <li v-for="social of socialLinks">
              <a :href="social.href"><img :src="getImagePath(social.img)" alt=""></a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>


<style lang="scss" scoped>
  @use '../style/partials/variables' as *;
  @use '../style/partials/mixin' as *;
  .footer-top{
    background-image: url("../assets/img/footer-bg.jpg");
    background-size: cover;
    color: white;
    .container {
      display: flex;
      height: 370px;
      background-image: url("../assets/img/dc-logo-bg.png");
      background-position:right;
      background-repeat: no-repeat;
      .link-area {  
        padding: 30px 0;
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;

        .links:nth-child(1) {
          margin-bottom: 15px;
        }
        .links {
          height:min-content;
          width: calc(calc(100%/3)/3);
          min-width: 130px;
          
          h4{
            text-transform: uppercase;
            font-size: 20px;
            margin-bottom: 15px;
          }
          ul {
            list-style: none;
            li {
              margin-bottom: 5px;
            }
            a{
              color: grey;
              text-decoration: none;
              font-size: 13px;
            }
          }
        }
      }
    }
  }
    
  .footer-bottom {
    background-color: rgb(48, 48, 48);
    color: white;
    .container {
      @include centerFlex('vertical');
      justify-content: space-between;
      .button {
        border: 2px solid $primary-color;
        padding: 15px;
        a {
          color: white;
          text-transform: uppercase;
          text-decoration: none;
        }
      }
      .social-links{
        padding: 30px 0;
        @include centerFlex('vertical');
        h4 {
          text-transform: uppercase;
          margin-right: 20px;
          color: $primary-color;
        }
        ul{
          display: flex;
          list-style: none;
          li {
            margin: 0 5px;
          }
        }
      }
    }
  }
</style>