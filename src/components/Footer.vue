<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__content">
        <div class="footer__left">
          <h3 class="footer__title">© 2021 - Stan’s Assets. All Right Reserved</h3>    
        </div>
        <div class="footer__right">
          <h3 class="footer__title">Privacy policy</h3>
          <h3 class="footer__title">Cookies policy</h3>    
        </div>     
      </div>    
    </div>     
  </footer>  
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
 @import "@/styles/mixins.scss";  

.footer {
  background: #fff;
  width: 100%;
  padding: 20px 0;

  @include tablets() {
    display: none;
  }

  &__content {
    display: flex;    
  }

  &__left {
    margin-right: auto;    
  }

  &__title {
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
    color: #4C4C4C;
   
    &:last-child {
      margin-left: 142px;    
    }      
  }

  &__right {
    display: flex;
    margin-left: auto;    
  }
}
</style>