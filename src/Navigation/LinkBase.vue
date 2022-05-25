<template>
  <a 
  class="nav-link"
  @click="linkTo"
  :class="{
    'nav-link__menu' : style === 'menu',
    'nav-link__active' : style === 'active',
    'nav-link__icons'  : style === 'icons',
    'nav-link__footer' : style === 'footer'  
  }"
  >
    <slot />
  </a>  
</template>

<script>
export default {
  emits:['click'],
  props: {
    style: String  
  },
  methods: {
    linkTo() {
      this.$emit('click')    
    }    
  }
}
</script>

<style lang="scss" scoped>

@import "@/styles/mixins.scss";
.nav-link {
  padding-right: 36px;
  font-weight: 700;
  position: relative;
  font-size: 16px;
  line-height: 36px;
  color: #fff;
  text-transform: uppercase;

  @include desktop() {
    font-size: 12px;
    
  }

  @include tablets() {
    
  }

  @include phones() {

  }

  &:hover {
    cursor: pointer;
  }

  &:after {
    content: "";
    display: block;
    position: absolute;
    left: 0;
    bottom: -1px;
    width: 0;
    height: 2px;
    background-color: #fff;
    transition: width 0.5s;  
  }

  &:hover::after {
    content: "";
    width: 70%;
    display: block;
    position: absolute;
    left: 0;
    bottom: -3px;
    height: 2px; 
    background-color: #fff; 
    transition: width 0.5s;  
  }

  &__menu {
   &:hover {
      color: #00A4E8;
      cursor: pointer; 
    }
  
   &::after {
      content: none;
    }
   
   &:hover::after {
      content: none;  
    } 
    
    @include phones() {
      padding-bottom: 10px;
      font-size: 12px;
      line-height: 20px;
    }
  }

  &__icons {
    padding: 12px;
    display: flex;
    justify-content: center;
    background: #FFFFFF;
    box-shadow: 0px 2px 12px 1px rgba(29, 51, 107, 0.25);
    border-bottom: 1px solid rgba(25,68,132, 0.1);
   
   &:first-child {
      border-top-left-radius: 3px;
      border-top-right-radius: 3px;
    }
  
   &:last-child {
      border-bottom-left-radius: 3px;
      border-bottom-right-radius: 3px;  
    }
   
   &::after {
      content: none;
    }
  
   &:hover::after {
      content: none;  
    }
   
   &:hover {
      background-color: #c4bdbd;
      transition: 0.5s;  
    }    
  }
 
  &__active {
    color: #00A4E8;
  }
 
  &__footer {
    font-weight: 400;
    font-size: 16px;
    line-height: 20px;
    color: #FFFFFF;
    margin-bottom: 18px;
   
    &::after {
      content: none;
    }
    
    &:hover::after {
      content: none;  
    }         
  }
}

</style>