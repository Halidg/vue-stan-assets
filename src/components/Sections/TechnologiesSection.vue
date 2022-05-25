<template>
  <section class="technologies">
    <div class="container">
      <div class="technologies__content">
        <h2 class="technologies__title">Technologies</h2>
        <p class="technologies__description"><span class="blue">Stan’s</span> <span class="dark-blue">Assets</span> is a team of developers that are committed to developing</p>
        <p class="technologies__description">high quality and engaging entertainment software</p>
      <div class="technologies__icons"> 
        <div class="technologies__icon" v-for="(item, idx) in cases" :key="idx">
          <img :src="item.url" alt="icon">
        </div>  
      </div>
      <p class="technologies__description">Our engineers develop applications for the most popular platforms.</p>  
      <div class="technologies__card">
        <div class="technologies__logo">
          <img class="tehnologies__img" src="@/assets/sections/technologies/technologies-logo.svg" alt="image37">  
        </div>
        <div class="technologies__review">
        <span class="technologies__span">4.5</span>
        <img class="tehnologies__img" src="@/assets/sections/technologies/technologies-stars.svg" alt="Star2">
        <span class="technologies__span">2 reviews</span>
        </div>
        <div class="technologies__action">
          <Button class="technologies__btn" :theme="'fill'">Check out reviews</Button>
        </div>
      </div>
      </div>    
    </div>
  </section>  
</template>

<script>
import Button from '@/UI/Button.vue'

export default {
  components: {
    Button  
  },
  data() {
    return {
      cases: [
        { url: require('@/assets/sections/technologies/technologies-android.svg')},
        { url: require('@/assets/sections/technologies/technologies-apple.svg')},
        { url: require('@/assets/sections/technologies/technologies-unity.svg')}
      ]
    }  
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";

.technologies {
  padding-top: 109px;  
  background: #fff;

  @include tablets () {
    padding-top: 65px;
  }

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;    
  }

  &__title {
    text-transform: uppercase;
    font-weight: 700;
    font-size: 36px;
    line-height: 39px;
    color: #194484;
    padding-bottom: 60px;

    @include desktop() {
      font-size: 24px;  
    }

    @include phones() {
      font-size: 22px;
      padding-bottom: 30px;  
    }
   
  }

   &__description {
    font-weight: 400;
    font-size: 24px;
    line-height: 38px;
    color: #242424; 
    
    @include desktop() {
      font-size: 18px;
    }

    @include phones() {
      text-align: center;
      line-height: 28px;
    }
  }

   &__icons {
    display: flex;
    margin-top: 30px;
    margin-bottom: 30px;
  }

   &__icon {
    background: #06B25F;
    box-shadow: 0px 4px 12px rgba(41, 24, 111, 0.2);
    border-radius: 16px;
    padding: 16px;
    margin-right: 60px;

    &:nth-child(2) {
      background: #276ED8;
    }

    &:nth-child(3) {
      background: #84B5FF;

      @include phones() {
        margin-right: 0px;
      }
    }

    @include desktop() {
      padding: 10px;
    }
  }

  &__card {
    display: flex;
    background: #FFFFFF;
    justify-content: center;
    box-shadow: 0px 3px 16px 2px rgba(29, 51, 107, 0.15);
    border-radius: 16px;
    margin-top: 120px;

    @include tablets() {
      flex-direction: column;
      margin-top: 70px;  
    }
  }

  &__logo {
    margin-right: auto;
    padding: 35px;

    @include desktop() {
      padding: 15px;
      margin: 0 auto;
    }
  }

  &__review {
    display: flex;
    align-items: center;

    @include tablets() {
      padding: 0 10px;
    }
  }

  &__span {
    font-weight: 400;
    font-size: 16px;
    line-height: 26px;
    padding-left: 15px;
    
    @include tablets() {
      font-size: 16px;
      padding-left: 2px;
    }  
  }
  
  &__action {
    display: flex;
    align-items: center;
    margin-left: auto;
    padding-left: 90px;
    padding-right: 33px;

    @include tablets() {
      margin: 0 auto;
      padding-top: 15px;
      padding-left: 0px;
      padding-right: 0px;
      padding-bottom: 15px;
    }
  }

  &__btn {
    @include tablets() {
      font-size: 12px;
      padding: 3px 10px; 
    }  
  }
}
</style>