<template>
  <section class="main">
    <div class="swiper-container" ref='slider'>
      <div class="swiper-wrapper">
        <div class="swiper-slide main__slide" v-for="(item, idx) in cases" :key="idx">
          <img class="main__img" :src='item.url'>
          <div class="container">
            <div class="main__content">
              <h1 class="main__title" v-html="item.title"></h1>
              <p class="main__description" v-html="item.description"></p>
              <div class="main__buttons">
                <Button class="main__btn">MORE</Button>
                <Button class="main__btn" :theme="'fill'">CONTACT US</Button>
              </div>
            </div>
            <div class="swiper-pagination-wrapper" ref="pagination"></div>
          </div>
        </div>
      </div>
    </div>
    <Icons class="main__icon" />
    <p class="main__description_mobile">We’re an Indian software development <br> company focused on just one  thing - <br> offshore software development services. <br> We have 16+ years of  experience and a <br> team of 450+ developers working <br> efficiently to  deliver unique solutions to <br> start-ups, software development <br> companies, enterprises, and digital <br> agencies to simplify their IT  outsourcing <br> experience & reduce time/cost to <br> market.</p>
  </section>
</template>

<script>
import Button from '@/UI/Button.vue'
import Swiper from 'swiper/bundle'
import Icons from '@/UI/Icons.vue'

export default {
  components: {
    Button,
    Icons
  },
  data() {
    return {
      slider: null,
      cases: [
        {
          title: 'FOCUS ON THE PRODUCT <br> AND LET US DO THE REST!', 
          description: 'We’re an Indian software development company focused on just one <br> thing - offshore software development services. We have 16+ years of <br> experience and a team of 450+ developers working efficiently to <br> deliver unique solutions to start-ups, software development <br> companies, enterprises, and digital agencies to simplify their IT <br> outsourcing experience & reduce time/cost to market.',
          url: require('@/assets/sections/main/intro-1.png')
        },
        {
          title: 'FOCUS ON THE PRODUCT <br> AND LET US DO THE REST!', 
          description: 'We’re an Indian software development company focused on just one <br> thing - offshore software development services. We have 16+ years of <br> experience and a team of 450+ developers working efficiently to <br> deliver unique solutions to start-ups, software development <br> companies, enterprises, and digital agencies to simplify their IT <br> outsourcing experience & reduce time/cost to market.',
          url: require('@/assets/sections/main/intro-2.png')
        },
        {
          title: 'FOCUS ON THE PRODUCT <br> AND LET US DO THE REST!', 
          description: 'We’re an Indian software development company focused on just one <br> thing - offshore software development services. We have 16+ years of <br> experience and a team of 450+ developers working efficiently to <br> deliver unique solutions to start-ups, software development <br> companies, enterprises, and digital agencies to simplify their IT <br> outsourcing experience & reduce time/cost to market.',
          url: require('@/assets/sections/main/intro-3.png')
        },
      ]
    }
  },
  methods: {
    initSlider() {
      const config = {
        slidesPerView: 1,
        spaceBetween: 0,
        pagination: {
          el: this.$refs.pagination,
          clickable: true,
          renderBullet: function (index) {
            return '<span class="swiper-pagination-bullet"></span>'
          },
        },
      }
      this.slider = new Swiper(this.$refs.slider, config)
      this.updateSlider()
    },
    async updateSlider() {
      if (!this.slider) {
        return
      }
      await this.$nextTick()
      this.slider.update()
    },  
  },
  destroyed() {
    this.slider?.destroy(true, true)
  },
  mounted() {
    this.initSlider()
  }
}
</script>

<style lang="scss" scoped>
 @import "@/styles/mixins.scss";
 
.main {
  position: relative;

  &__slide {
    padding-top: 227px;
    padding-bottom: 258px;

    @include desktop() {
      padding-top: 100px;             
    }

    @include phones() {
      padding-top: 60px;
      padding-bottom: 100px;      
    }
  }

  &__img {
    position: absolute;
    width: 100%;
    top: 0;
    left: 0;
  }

  &__content {
    position: relative;
    display: flex;
    flex-direction: column;
    z-index: 10;
  }

  &__title {
    font-weight: 700;
    font-size: 44px;
    line-height: 60px;
    color: white;

    @include desktop() {
      text-align: center;          
    }

    @include tablets() {
      font-size: 24px;
      line-height: 30px;  
    }

    @include phones() {
      font-size: 14px;
      line-height: 18px;  
    }
  }

  &__description {
    font-weight: 400;
    font-size: 16px;
    line-height: 26px;
    color: #fff;
    padding-top: 25px;

    @include desktop() {
      text-align: center;
      padding-bottom: 15px;          
    }

    @include tablets() {
      padding-top: 15px;
      line-height: 20px;
    }

    @include phones() {
      display: none;  
    }
  }

  &__description_mobile {
    font-weight: 400;
    font-size: 14px;
    line-height: 26px;
    color: #000;
    display: none;
    text-align: center;
    
    
    @include phones {
      display: block;
    }
  }

  &__buttons {
    margin-top: 25px;
    display: flex;

    @include desktop() {
      margin: 0 auto;  
    }

    @include tablets() {
      margin-top: 0;   
    }

    @include phones() {
      margin-bottom: 15px;
    }
  }

  &__btn {
    margin-right: 15px;
   
    @include phones() {
      font-size: 10px;
      padding: 3px 25px;
    }
  }
  
  &__icon {
    @include tablets() {
      display: none;  
    }    
  }
}
</style>