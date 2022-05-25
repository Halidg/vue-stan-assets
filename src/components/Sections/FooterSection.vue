<template>
  <section class="section-footer" id="footer">
    <div class="container">
      <div class="section-footer__content">
        <div class="section-footer__logo">
          <Logo></Logo>
          <div class="section-footer__icons">
            <img class="section-footer__icon" :src="item.url" alt="icon" v-for="(item, idx) in images" :key="idx">      
          </div>    
        </div>
        <div class="section-footer__item">
         <h2 class="section-footer__title">Services</h2>
          <div class="section-footer__item_block">
            <link-base class="section-footer__link" :style="'footer'" v-for="(item,idx) in links" :key="idx">{{item.title}}</link-base>    
          </div>    
        </div> 
        <div class="section-footer__item">
         <h2 class="section-footer__title">Technologies</h2>
          <div class="section-footer__item_block">
            <link-base class="section-footer__link" :style="'footer'">Android</link-base>
            <link-base class="section-footer__link" :style="'footer'">IOS</link-base>
            <link-base class="section-footer__link" :style="'footer'">Unity</link-base>    
          </div>    
        </div>
        <div class="section-footer__item">
          <h2 class="section-footer__title_products">Products</h2>
          <h2 class="section-footer__title_products">Portfolio</h2>
          <h2 class="section-footer__title_products">Blog</h2>    
        </div>
        <div class="section-footer__item">
         <h2 class="section-footer__title">About us</h2>
          <div class="section-footer__item_block">
            <link-base class="section-footer__link" :style="'footer'">Contacts</link-base>
            <link-base class="section-footer__link" :style="'footer'">Team</link-base>
            <link-base class="section-footer__link" :style="'footer'">Join the Team</link-base>    
          </div>    
        </div>   
      </div>
    </div>
  </section>
  <Footer></Footer>
</template>


<script>
import LinkBase from '../../Navigation/LinkBase.vue'
import Footer from '../Footer.vue'
import Logo from '@/UI/Logo'

export default {
  components: {
    LinkBase,
    Footer,
    Logo, 
  },  
  data() {
    return {
      images: [
        {url: require('@/assets/sections/footer/footer-1.svg')},
        {url: require('@/assets/sections/footer/footer-2.svg')},
        {url: require('@/assets/sections/footer/footer-3.svg')},
        {url: require('@/assets/sections/footer/footer-4.svg')},
        {url: require('@/assets/sections/footer/footer-5.svg')},    
      ],
      links: [
        {title: 'Mobile Application Development'},
        {title: 'Game Development Outsourcing'},
        {title: 'VR App Development'},
        {title: 'Dedicated Developers'},
        {title: 'SDK Development'},
        {title: '3D Modeling services'},    
      ]    
    }    
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";

.section-footer {
  padding-top: 410px;
  background-image: url('../../assets/sections/footer/footer-background.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;

  @include phones() {
    padding-top: 85px;
    background-image: url('../../assets/sections/footer/footer-background-mobile.svg');
  }
  
  &__content {
    display: flex;

    @include tablets() {
      flex-direction: column;  
    }
  }

  &__logo {
    display: flex;
    flex-direction: column;
    margin-right: auto;

    @include phones() {
      margin: 0 auto;
    }
  }

  &__icons {
    display: grid;
    grid-template-columns: repeat(3, 1fr); 
    grid-column-gap: 45px; 
    grid-row-gap: 44px; 
    margin-top: 45px;
    
    @include tablets() {
     grid-template-columns: repeat(5, 1fr);
     grid-column-gap: 65px;
     margin-bottom: 67px;
    }

    @include phones() {
     grid-column-gap: 25px;
    }
  }

  &__icon {
    @include phones() {
      width: 30px;
    }
  }

  &__item {
    display: flex;
    flex-direction: column;
    margin: 0 auto;

    @include desktop() {
      margin-left: 25px;  
    }

    @include tablets() {
      margin-right: auto;
    }
  }

  &__title {
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 21px;
    text-transform: uppercase;
    color: #FFFFFF;

    @include tablets() {
      font-size: 18px;
    }
  }

  &__title_products {
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 21px;
    text-transform: uppercase;
    color: #FFFFFF;
    margin-bottom: 24px;
    
    @include tablets() {
      font-size: 18px;
    }
  }

  &__item_block {
    display: flex;
    flex-direction: column;
    margin-top: 30px;
    margin-left: 20px;

    @include tablets() {
      margin-left: 10px;
      padding-bottom: 34px;
    }
  }
}
</style>