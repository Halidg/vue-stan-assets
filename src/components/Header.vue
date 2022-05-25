<template>
  <header class="header"  @scroll="scrollEvent" :class="{'header_scroll': scrollHandler}">
    <div class="container">
      <div class="header__content">
        <div class="header__logo">
          <Logo />
        </div>
          <Navigation />
        <div class="header__action">
          <Button class="header__btn">CONTACT US</Button>
        </div>
        <div class="header__burger">
          <Burger @click-burger="showMenu" :show="showing" />
        </div>
      </div>
         <BurgerMenu :show="showing">
           <Navigation :style="'mobile'"/> 
         </BurgerMenu>
    </div>
  </header>  
</template>

<script>
import Button from '@/UI/Button.vue'
import Logo from '@/UI/Logo.vue'
import Navigation from '@/Navigation/Navigation.vue'
import BurgerMenu from '@/UI/BurgerMenu.vue'
import Burger from '@/UI/Burger.vue'

export default {
  components: {
    Button,
    Logo,
    Navigation,
    BurgerMenu,
    Burger  
  },
  data() {
    return {
      scrollHandler: false,
      showing: false  
    }  
  },
  created() {
    window.addEventListener('scroll', this.scrollEvent)
  },
   destroyed() {
    window.removeEventListener('scroll', this.scrollEvent);
  },
  methods: {
    scrollEvent() {
      this.scrollHandler = window.scrollY > 1    
    },
    showMenu() {
      this.showing = !this.showing 
      console.log('help'); 
    }  
  },
  computed: {
    burgerSrc() {
      return this.showing ? require('@/assets/icons/close.svg') : require('@/assets/icons/burger.svg') 
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.header {
  width: 100%;
  position: fixed;
  z-index: 1000;
  background: rgba(33, 33, 33, 0.3);
  box-shadow: 0px 4px 12px rgba(24, 9, 96, 0.1);
  transition: 0.5s;
  padding: 19px 0;

  @include phones() {
    padding: 5px 0;                 
  }

  &_scroll {
    background: #708090;
  }

  &__content {
    display: flex;
    justify-content: center;
    align-items: center;   
  }

  &__logo {
    margin-right: auto;
    z-index: 1000;
  }

  &__action {
    margin-left: auto;
  }

  &__btn {
    @include desktop() {
      padding: 10px 10px;
      font-size: 10px;                
    }

    @include tablets() {
      display: none;
    }
  }

  &__burger {
    display: none;
    
    @include tablets() {
      display: block;
      z-index: 1000;  
    }
  }
}
</style>