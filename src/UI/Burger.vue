<template>
  <button class="burger" :class='{"open": show}' @click="$emit('click-burger')">
    <span class="line line-1"></span>
    <span class="line line-2"></span>
    <span class="line line-3"></span>
  </button>  
</template>

<script>
export default {
  name: 'UiBurger',
  props: {
    show: {
      type: Boolean,
      default: false
    },
  },
}
</script>

<style scoped lang="scss">
.burger {
  width: 33px;
  height: 25px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background: transparent;
  outline: none;
  border: 0;
  padding: 0;
  cursor: pointer;
}
.line {
  display: block;
  height: 2px;
  width: 100%;
  border-radius: 10px;
  background: #fff;
  &-1 {
    transform-origin: 0% 0%;
    transition: transform 0.4s ease-in-out;
  }
  &-2 {
    transition: transform 0.2s ease-in-out;
  }
  &-3 {
    transform-origin: 0% 100%;
    transition: transform 0.4s ease-in-out;
  }
}
.open {
  .line-1 {
    transform: rotate(45deg);
  }
  .line-2 {
    transform: scaleY(0);
  }
  .line-3 {
    transform: rotate(-45deg);
  }
}
</style>