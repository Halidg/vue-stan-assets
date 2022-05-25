<template>
  <form class="form" @submit.prevent="submitForm">
    <input class="form__input" type="text" placeholder="Name">
    <input class="form__input" type="text" placeholder="Email">
    <textarea class="form__textarea" placeholder="Message"></textarea>
    <Button class="form__btn" :theme="'fill'">Send request</Button>      
  </form>  
</template>

<script>
import Button from '../UI/Button.vue'

export default {
  components: {
    Button    
  }
}
</script>

<style lang="scss" scoped>
@import "@/styles/mixins.scss";

.form {
  display: flex;
  flex-direction: column;
  padding: 70px;

  @include tablets() {
    padding: 35px;  
  }

  &__input {
    background: #FFFFFF;
    border: 1px solid #D7D7D7;
    border-radius: 4px;
    margin-bottom: 20px;
    padding: 10px;
    font-size: 16px;

    @include tablets() {
      padding: 5px;
    }
  }  
  
  &__textarea {
    background: #FFFFFF;
    border: 1px solid #D7D7D7;
    font-size: 16px;
    border-radius: 4px;
    resize: none;
    padding: 20px;
    
    @include tablets() {
      padding: 10px;
    }
  }
  ::placeholder {
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
    color: #A9A9A9;        
  }

  &__btn {
    margin-top: 30px;
    margin-bottom: 50px;
    padding: 10px;
    
    @include tablets() {
      padding: 5px;
    }

    @include phones() {
      font-size: 14px;
    }
  }
}
</style>