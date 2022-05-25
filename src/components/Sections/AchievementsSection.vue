<template>
  <section class="achievements" id='achievements'>
    <div class="container">
     <h2 class="achievements__title">achievements</h2>
      <div class="achievements__content">
        <div class="achievements__card" v-for="(item, idx) in cases" :key="idx">
          <img class="achievements__img" :src="item.url" alt="">
          <p class="achievements__subtitle" v-html="item.description"></p>
        </div>  
      </div>    
    </div>
  </section>  
</template>

<script>
export default {
  data() {
    return {
      cases: [
        { 
          description: 'Collaboration with Moon Studios <br> on WotW AAA Unity game.',
          url: require('@/assets/sections/achievements/achievements-1.svg')         
        },
        { 
          description: '50+ successfully launched projects on the the market.',
          url: require('@/assets/sections/achievements/achievements-2.svg')         
        }
        ,
        { 
          description: 'Asset store publisher since 2013',
          url: require('@/assets/sections/achievements/achievements-3.svg')         
        }
        ,
        { 
          description: 'Our products (packages) used by 100k+ devs in 5k+ commercial projects worldwide',
          url: require('@/assets/sections/achievements/achievements-4.svg')         
        }                
      ]  
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.achievements {
  padding-top: 128px;

  @include phones() {
    padding-top: 55px;
  }

  &__title {
    font-weight: 400;
    font-size: 36px;   
    line-height: 39px;
    text-transform: uppercase;  
    color: #194484;
    text-align: center;

    @include phones() {
      font-size: 22px;  
    }
  }

  &__content {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-column-gap: 25px; 
    grid-row-gap: 35px; 
    width: 100%;
    margin-top: 100px;
    
    @include desktop() {
      grid-template-columns: repeat(2, 1fr);    
    }

    @include phones() {
      grid-template-columns: repeat(1, 1fr);
      margin-top: 50px;  
    }
  }

  &__card {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    background: rgba(39, 110, 216, 0.05);
    border-radius: 16px;
    height: 400px;
    padding: 0 20px;
  }

  &__img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    @include tablets() {
      max-width: 100%;
    }
  }

  &__subtitle {
    font-weight: 700;
    font-size: 16px;
    line-height: 26px;
    text-align: center;
    color: #242424;
    z-index: 1;
    margin-bottom: 65px;

    @include phones() {
      margin-bottom: 25px;
    }
  }
}
</style>
