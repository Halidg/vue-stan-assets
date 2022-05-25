<template>
  <div class="menu" :class="{'menu_show': show}">
     <slot />
     <Button class="menu__btn">CONTACT US</Button>      
  </div>    
</template>

<script>
import Button from '@/UI/Button.vue'
import Navigation from '@/Navigation/Navigation.vue'

export default {
  props: {
    show: Boolean
  },
  components: {
    Button,
    Navigation  
  },
}
</script>

<style lang="scss" scoped>
.menu {
  position: fixed;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: center;
  flex-direction: column;
  padding: 55px 85px;
  background-color: rgb(132, 158, 173);
  transition-duration: 500ms;

  &_show {
    left: 0;
  }

  &__btn {
    padding: 3px 10px;
    font-size: 12px;  
  }
}
</style>