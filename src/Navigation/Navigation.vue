<template>
  <nav class="nav" :class="{
    'nav__mobile' : style === 'mobile'
  }">
    <link-drop-down>SERVICES</link-drop-down>
    <link-drop-down>TECHNOLOGIES</link-drop-down>
    <link-scroll scrollTo='services'>PRODUCTS</link-scroll>
    <link-scroll scrollTo='achievements'>PORTFOLIO</link-scroll>
    <link-scroll scrollTo='footer'>Faq</link-scroll>
    <link-drop-down>ABOUT US</link-drop-down>
  </nav>  
</template>

<script>
import LinkDropDown from './LinkDropDown.vue'
import LinkScroll from './LinkScroll.vue'

export default {
  props:{
    style: String
  },
  components: {
    LinkDropDown,
    LinkScroll    
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";

.nav {
  display: flex;
  margin-top: 10px;
  position: relative;

  @include tablets() {
    display: none;           
  }
  
  &__mobile {
    display: flex;
    flex-direction: column;  
  }
}

</style>