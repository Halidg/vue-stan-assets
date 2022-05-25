<template>
  <section class="partnership">
    <div class="container">
      <div class="partnership__content">
        <h2 class="partnership__title">LOOKING FOR A PARTNER IN BUILDING A SOLUTION?</h2>
        <p class="partnership__subtitle">We are ready to discuss your project requirements</p>
        <Button class="partnership__button" :theme="'outline'">Let’s talk</Button>
      </div>    
    </div>
  </section>  
</template>

<script>
import Button from '@/UI/Button.vue'

export default {
  components: {
    Button    
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
 
.partnership {
  padding-top: 238px;
  padding-bottom: 350px;
  background-image: url('../../assets/sections/partnership/partnership-background.svg');
  background-repeat: no-repeat;
  background-position: center;  
  background-size: cover;

  @include phones() {
    background-image: url('../../assets/sections/partnership/partnership-background-mobile.svg'); 
  }
  
  &__content {
    display: flex;
    flex-direction: column;
  }

  &__title {
    font-weight: 400;
    font-size: 44px;
    line-height: 60px;
    text-transform: uppercase;
    color: #FFFFFF;
    
    @include desktop() {
      font-size: 30px;
      text-align: center;
    }

    @include tablets() {
      font-size: 25px;
    }

    @include phones() {
      font-size: 18px;  
      line-height: 20px;
    }
  }

  &__subtitle {
    font-weight: 400;
    font-size: 24px;
    line-height: 29px;
    text-align: center;
    color: #FFFFFF;
    margin-top: 16px;
    margin-bottom: 36px;
    
    @include tablets() {
      font-size: 20px;
    }

    @include phones() {
      font-size: 14px;  
    }
  }

  &__button {
    margin: 0 auto;    
  }
}
</style>