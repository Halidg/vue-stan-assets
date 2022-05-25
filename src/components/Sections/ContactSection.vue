<template>
  <section class="contact">
    <div class="container">
      <h2 class="contact__title">Contacts</h2>
      <h3 class="contact__subtitle">We are open for dialog and you are welcome to share your opinions or thoughts with us</h3>
      <p class="contact__description">Hit us up any time through email with any idea and help us turn your great ideas into brilliant projects</p>
        <div class="contact__content">
          <div class="contact__left">
            <div class="contact__wrapper" v-for="(item, idx) in cases" :key="idx">
              <img class="contact__img" :src="item.url" alt="contact"> 
              <p class="contact__info">{{item.info}}</p> 
            </div>
          </div>
          <div class="contact__right">
            <Form />      
          </div>
          <img class="contact__svg" src="@/assets/sections/contacts/contact-7.svg" alt="">
          <img class="contact__svg_2" src="@/assets/sections/contacts/contact-8.svg" alt="">
        </div>
    </div>        
  </section>  
</template>

<script>
import Form from '@/UI/Form.vue'

export default {
  components: {
    Form  
  },
  data() {
    return {
      cases: [
        {
          url: require('@/assets/sections/contacts/contact-1.svg'),
          info: 'Russia,Moscow,Tverskaya'
        },
        {
          url: require('@/assets/sections/contacts/contact-2.svg'),
          info: '+38 (093) 345 56 76'
        },
        {
          url: require('@/assets/sections/contacts/contact-3.svg'),
          info: '+38 (093) 345 56 77'
        },
        {
          url: require('@/assets/sections/contacts/contact-4.svg'),
          info: 'Stanassets'
        },
        {
          url: require('@/assets/sections/contacts/contact-5.svg'),
          info: 'stanAssets@gmail.com' 
        },
        {
          url: require('@/assets/sections/contacts/contact-6.svg'),
          info: 'facebook.com/Stanassets'
        }
      ]  
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.contact {
  padding-top: 264px;
  padding-bottom: 269px;

  @include tablets() {
    padding-bottom: 100px;
  }

  @include phones() {
    padding-top: 150px;
    padding-bottom: 50px;  
  }
  
  &__title {
    font-style: normal;
    font-weight: 400;
    font-size: 36px;
    line-height: 39px;
    text-transform: uppercase;
    text-align: center;
    color: #194484;
    
    @include phones() {
      font-size: 24px;
    }
  }

  &__subtitle {
    font-weight: 700;
    font-size: 24px;
    line-height: 29px;
    text-align: center;
    color: #242424;
    margin-top: 60px;
    
    @include phones() {
      font-size: 18px;
      margin-top: 34px;
    }
  }

  &__description {
    font-weight: 400;
    font-size: 16px;
    line-height: 26px;
    text-align: center;
    color: #242424;
    margin-top: 20px;
    
    @include phones() {
      margin-bottom: 32px;
    }
  }

  &__content {
    display: flex; 
    position: relative;

    @include phones() {
      flex-direction: column;  
    }
  }

  &__left {
    display: flex;
    flex-direction: column;
    margin-right: auto;
    margin-top: 148px;
    
    @include phones() {
      margin: 0 auto;
      padding-bottom: 67px;  
    }
  }

  &__wrapper {
    display: flex;
    margin-bottom: 35px;
  }

  &__info {
    font-weight: 400;
    font-size: 20px;
    line-height: 24px;
    display: flex;
    align-items: center;
    text-transform: capitalize;
    color: #242424;
    margin-left: 21px;
    
    @include phones() {
      font-size: 18px;
    }
  }

  &__right {
    margin-left: auto;
    margin-top: 148px;
    background: #FFFFFF;
    box-shadow: 0px 3px 16px 2px rgba(29, 51, 107, 0.15);
    border-radius: 6px;
    width: 40%;
    z-index: 100;

    @include phones() {
      margin: 0 auto;
      width: 90%;  
    }
  }

  &__svg {
    position: absolute;
    left: 55%;
    top: 15%;

    @include phones() {
      display: none;  
    }
  }

  &__svg_2 {
    position: absolute;
    left: 52%;
    top: 75%;

    @include phones() {
      display: none;  
    }
  }
}
</style>