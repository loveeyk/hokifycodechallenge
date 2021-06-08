<template>
  <div class="contact">
      <span>Contact</span>
  </div>
</template>

<script>
import { Vue } from "vue-class-component";

export default class Contact extends Vue{

}
</script>

<style lang="scss">
.contact{
display: flex;
justify-content: center;
align-items:center;
height: 100vh;
  span{
    font-size: 20vw;
  }
}
</style>