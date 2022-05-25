<template>
  <section class="services" id='services'>
    <div class="container">
      <div class="services__content">
        <h2 class="services__title">Services</h2>
          <div class="services__wrapper" v-for="(item, idx) in cases" :key="idx" :class="{'services__wrapper_reverse' : idx % 2}">
            <div class="services__left">
              <h3 class="services__item_title">{{item.title}}</h3>
              <p  class="services__item_subtitle" v-html="item.mobile"></p>
            </div>
            <div class="services__right">
              <img class="services__img" :src="item.url" alt="Illustration">
            </div>
          </div>
      </div>    
    </div>
  </section>  
</template>

<script>
export default {
  name: "SectionServices",
  data() {
    return {
      mobile: null
    }
  },
  computed: {
    cases() {
      return [
        {
          title: 'GAME DEVELOPMENT',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis <br> dapibus purus, viverra porta velit. Nam eleifend, dolor a <br> condimentum ullamcorper, ligula nunc elementum mi, et mollis <br> odio ligula eu felis. Vestibulum a libero lorem. Nulla vestibulum id elit <br> in ullamcorper. Fusce pellentesque tortor velit, eu rutrum nunc <br> eleifend quis. Fusce dignissim, lectus ut tristique convallis, leo justo <br> tempus erat, at volutpat arcu tellus eget sapien. Aliquam non ligula <br> in ligula malesuada venenatis.Fusce lacus felis, efficitur ut euismod <br> ac, gravida sed tortor. Suspendisse vitae imperdiet elit, at viverra <br> magna. Aenean ut libero ut arcu maximus faucibus ut ut sapien.',
          mobile: 'With over 5 years of game development experience, we have all that it takes to develop a high quality product.',
          url: require('@/assets/sections/services/services-1.png'),
        },
        {
          title: 'SDK Development',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis <br> dapibus purus, viverra porta velit. Nam eleifend, dolor a <br> condimentum ullamcorper, ligula nunc elementum mi, et mollis <br> odio ligula eu felis. Vestibulum a libero lorem. Nulla vestibulum id elit <br> in ullamcorper. Fusce pellentesque tortor velit, eu rutrum nunc <br> eleifend quis. Fusce dignissim, lectus ut tristique convallis, leo justo <br> tempus erat, at volutpat arcu tellus eget sapien. Aliquam non ligula <br> in ligula malesuada venenatis.Fusce lacus felis, efficitur ut euismod <br> ac, gravida sed tortor. Suspendisse vitae imperdiet elit, at viverra <br> magna. Aenean ut libero ut arcu maximus faucibus ut ut sapien.',
          mobile: 'Stans Assets is one of the most popular developers within the Unity Asset Store. Want to test some of our amazing software? Check out one of our many plugins. We guarantee your satisfaction.',
          url: require('@/assets/sections/services/services-2.png'),
       },
        {
          title: '3D Modeling services',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis <br> dapibus purus, viverra porta velit. Nam eleifend, dolor a <br> condimentum ullamcorper, ligula nunc elementum mi, et mollis <br> odio ligula eu felis. Vestibulum a libero lorem. Nulla vestibulum id elit <br> in ullamcorper. Fusce pellentesque tortor velit, eu rutrum nunc <br> eleifend quis. Fusce dignissim, lectus ut tristique convallis, leo justo <br> tempus erat, at volutpat arcu tellus eget sapien. Aliquam non ligula <br> in ligula malesuada venenatis.Fusce lacus felis, efficitur ut euismod <br> ac, gravida sed tortor. Suspendisse vitae imperdiet elit, at viverra <br> magna. Aenean ut libero ut arcu maximus faucibus ut ut sapien.',
          mobile: 'We pride ourselves on producing high quality graphics support. Providing experienced designers to any project, and offering affordable pricing for almost any budget.',
          url: require('@/assets/sections/services/services-3.png'),
        },
        {
          title: 'VR App Development',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis <br> dapibus purus, viverra porta velit. Nam eleifend, dolor a <br> condimentum ullamcorper, ligula nunc elementum mi, et mollis <br> odio ligula eu felis. Vestibulum a libero lorem. Nulla vestibulum id elit <br> in ullamcorper. Fusce pellentesque tortor velit, eu rutrum nunc <br> eleifend quis. Fusce dignissim, lectus ut tristique convallis, leo justo <br> tempus erat, at volutpat arcu tellus eget sapien. Aliquam non ligula <br> in ligula malesuada venenatis.Fusce lacus felis, efficitur ut euismod <br> ac, gravida sed tortor. Suspendisse vitae imperdiet elit, at viverra <br> magna. Aenean ut libero ut arcu maximus faucibus ut ut sapien.',
          mobile: 'Virtual Reality is the future of gaming. We have expertise that can create a professional and fluid virtual reality experience unlike anything you have ever seen.',
          url: require('@/assets/sections/services/services-4.png'),
        }
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.services {
  padding-top: 120px;
  padding-bottom: 42px;
  background-color: #fff;

  &__content {
    display: flex;
    flex-direction: column;    
  }

  &__title {
    text-align: center;
    font-weight: 400;
    font-size: 36px;
    line-height: 39px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #194484;
    
    @include desktop() {
      font-size: 24px;    
    }
  }

  &__wrapper {
    display: flex;
    justify-content: center;
    align-items: center;

    @include tablets() {
      flex-direction: column;  
    }
    
    &_reverse {
       justify-content: flex-end;
       .services__left {
          order: 1;
          
          @include tablets() {
            order: 0;
          }
       }
       .services__right {
         order: 0;
       }
    }
  }
  &__left {
    margin-top: 102px;

    @include tablets() {
      margin: 0 auto;
    }
  }

  &__right {
    margin-right: 113px;
    margin-top: 70px;
    
    @include tablets() {
      margin: 0 auto;
    }
  }

  &__item_title{
    font-weight: 400;
    margin-bottom: 4px;
    font-size: 24px;
    line-height: 38px;
    text-transform: uppercase;
    color: #0D6EB7; 
    
    @include tablets() {
      font-size: 15px;
      text-align: center;
      margin-top: 40px;
    }
  }

  &__item_subtitle {
    font-weight: 400;
    font-size: 16px;
    line-height: 26px;
    color: #242424;
    
    @include desktop() {
      font-size: 14px;  
    }

    @include tablets() {
      font-size: 12px;
    }
  }

  &__img {
     @include tablets() {
      width: 230px;
    }   
  }
}
</style>