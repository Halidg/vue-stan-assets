<template>
  <section class="partners">
    <div class="container">
      <h2 class="partners__title">Partners</h2>    
      <div class="partners__content" :class="[showing  ? 'partners__content show' : '']">
       <div class="partners__card" v-for="(item,idx) in cases" :key="idx">
          <img class="partners__img" :src="item.url" alt="">
       </div>
      </div>
      <div class="partners__wrapper">
        <p @click="showCards" class="partners__subtitle">{{textChange}}</p>
        <img @click="showCards" src="@/assets/icons/arrow-mobile.svg" alt="arrow">  
      </div>
    </div>    
  </section>  
</template>

<script>
export default {
  data() {
    return {
      cases: [
        { url: require('@/assets/sections/partners/partners-1.svg')},
        { url: require('@/assets/sections/partners/partners-2.svg')},
        { url: require('@/assets/sections/partners/partners-3.svg')},
        { url: require('@/assets/sections/partners/partners-4.svg')},
        { url: require('@/assets/sections/partners/partners-5.svg')},
        { url: require('@/assets/sections/partners/partners-6.svg')},
        { url: require('@/assets/sections/partners/partners-7.svg')},
        { url: require('@/assets/sections/partners/partners-8.svg')},
        { url: require('@/assets/sections/partners/partners-9.svg')},
        { url: require('@/assets/sections/partners/partners-10.svg')},
        { url: require('@/assets/sections/partners/partners-11.svg')},
        { url: require('@/assets/sections/partners/partners-12.svg')},
        { url: require('@/assets/sections/partners/partners-13.svg')},
        { url: require('@/assets/sections/partners/partners-14.svg')},
        { url: require('@/assets/sections/partners/partners-1.svg')},
        { url: require('@/assets/sections/partners/partners-5.svg')},   
      ],
      showing: false
    }    
  },
  methods: {
    showCards() {
      this.showing = !this.showing
    }  
  },
  computed: {
    textChange() {
      if (this.showing) {
       return 'Hide'  
      }
      
      return 'Show More'
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.partners {
  padding-top: 358px;

  @include phones() {
    padding-top: 150px;
  }
  
  &__content {
    display: grid; 
    grid-template-columns: repeat(4, 1fr); 
    grid-column-gap: 25px; 
    grid-row-gap: 25px; 
    margin-top: 80px;
    transition-duration: 500ms;
    
    @include desktop() {
      grid-template-columns: repeat(2, 1fr);  
    }

    @include phones() {
      grid-template-columns: repeat(2, 1fr);
      grid-row-gap: 15px;
      max-height: 475px;
      overflow-y: hidden;
      padding: 0 10px;
      margin-top: 40px;
    }
  }

  &__title {
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

  &__card {
    background: #FFFFFF;
    box-shadow: 0px 3px 16px 4px rgba(29, 51, 107, 0.1);
    border-radius: 16px;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 30px;

    @include phones() {
      box-shadow: 0px 2px 5px 2px rgba(29, 51, 107, 0.1);  
    }
  }

  &__img {
    @include phones() {
      width: 60px;
    }  
  }

  &__wrapper {
    display: none;
    justify-content: center;
    margin-top: 45px;
    
    @include phones() {
      display: flex;  
    }
  }

  &__subtitle {
    font-size: 14px;
    color: #194484;
  }
}

.show {
  max-height: 983px;
  overflow: visible;    
}
</style>