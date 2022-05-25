<template>
  <div class="wrapper">
    <link-base :style="active" @click="dropDown">
      <slot />
      <img  class="menu-arrow" src="@/assets/icons/arrow.svg" alt="Vector">
    </link-base>
    <div class="menu" v-show="showDropMenu">
      <link-base v-for="(item,idx) in items" :key="idx" :style="'menu'">{{item.title}}</link-base>
    </div>  
  </div>
   
</template>

<script>
import LinkBase from './LinkBase.vue'

export default {
  components: {
    LinkBase   
  },
  data() {
    return {
      showDropMenu: false,
      items: [
        {title: 'MOBILE APPLICATION DEVELOPMENT'},
        {title: 'GAME DEVELOPMENT OUTSOURCING'},
        {title: 'VR APP DEVELOPMENT'},
        {title: 'DEDICATED DEVELOPERS'},
        {title: 'SDK DEVELOPMENT'},
        {title: '3D MODELING SERVICES'},
        {title: 'AR APP DEVELOPMENT'}    
      ]   
    }    
  },
  computed:{
    active() {
      if (this.showDropMenu) {
        return 'active'
      }  
    }
  },
  methods: {
    dropDown() {
      this.showDropMenu = !this.showDropMenu
    }    
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";
.wrapper {
  position: relative;
}

.menu-arrow {
  margin-bottom: 2px;
  margin-left: 4px;
  
  &:hover {
    cursor: pointer;
  }
}

.menu {
  position: absolute;
  width: 344px;
  left: 0;
  top: 100%;
  display: flex;
  flex-direction: column;
  padding: 15px;
  border-top: 4px  solid #00A4E8;
  border-bottom-right-radius: 10px;
  border-bottom-left-radius: 10px;
  background: rgba(33, 33, 33, 0.8);
  box-shadow: 2px 4px 16px rgba(158, 158, 158, 0.3);

  @include tablets() {
    background: rgb(33, 33, 33);
    z-index: 1000;  
  }

  @include phones() {
    width: 210px;
  }
}
</style>