<template>
  <button 
    class="button"
    :class="{
      'button__fill' : theme === 'fill',
      'button__outline' : theme === 'outline'  
    }"
  >
    <slot />
  </button>
</template>

<script>
export default {
  props: {
    theme: String  
  }
}
</script>

<style lang="scss" scoped>
.button {
  margin-top: 5px;
  margin-bottom: 5px;
  border: 2px solid #FFFFFF;
  background: transparent;
  padding: 5px 35px;
  border-radius: 6px;
  color: white;
  font-weight: 700;
  font-size: 16px;
  line-height: 2.25;
  transition-duration: 0.2s;

  &:hover {
    cursor: pointer;
  }

  &__fill {
    background: #06B25F;
    border-radius: 6px;
    text-transform: uppercase;
    outline: none;
    border: none;

    &:hover {
     background: #036f3b;
    }
  }

  &__outline {
    border: 2px solid #06B25F;
    color: #06B25F;
    background: #FFFFFF;

    &:hover {
     background: #242424;
     opacity: 0.7;
    }    
  } 
}

</style>