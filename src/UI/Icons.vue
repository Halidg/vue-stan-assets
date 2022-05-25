<template>
  <div class="icons">
    <link-base :style="'icons'" v-for="(icon, idx) in icons" :key="idx">
      <img class="icons__img" :src="icon.url"  :alt="icon.alt">  
    </link-base>
  </div>  
</template>

<script>
import LinkBase from '../Navigation/LinkBase.vue'

export default {
  components: {
    LinkBase    
  },
  data() {
    return {
      icons: [
        {url: require('@/assets/icons/f.svg') , alt: 'f'},
        {url: require('@/assets/icons/in.svg'),  alt:'in'},
        {url: require('@/assets/icons/tel.svg'), alt: 'tel'},
        {url: require('@/assets/icons/skp.svg') , alt: 'skp'}   
      ]    
    }    
  }
}
</script>

<style lang="scss" scoped>
.icons {
  position: absolute;
  display: flex;
  flex-direction: column;
  right: 0%;
  top: 50%;
  z-index: 100;
  
  &__img {
    margin-bottom: 5px;
    margin-top: 5px;
    &:hover {
      cursor: pointer;    
    }
  }
}
</style>