<template>
  <div class="wrapper">
     <link-base @click="scroll">
    <slot/>
  </link-base>  
  </div>
</template>

<script>
import LinkBase from './LinkBase.vue'

export default {
  props: {
    scrollTo: String,
  },
  components: {
    LinkBase    
  },
  methods:{
    scroll() {
      const el = document.getElementById(this.scrollTo)

      if(el) {
        setTimeout(() => {el.scrollIntoView({behavior: 'smooth'})}, 0)
      }
    }    
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  position: relative;
}
</style>