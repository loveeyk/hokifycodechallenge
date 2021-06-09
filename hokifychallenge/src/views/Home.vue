<template>
  <HeroVue path="../assets/logo_lovify.svg"/>
  <div class="home">  
   <h1>Willkommen auf Lovify.</h1>
     <!-- <img src="../assets/logo_lovify.svg" alt="logo" /> -->
  <a href="contact">Click Me</a>

  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {
  },
})
export default class Home extends Vue {

   
   
}
</script>

<style lang="scss">
.home{
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  align-items: center;
  height: 70vh;
  a{
    padding: 1rem;
    background: #10b0af;
    color: white;
    text-decoration: none;
    border: 1px solid #cafcfc;
    box-shadow: 1px 2px 8px #96ffff;
    border-radius: 5px;
  }
}
</style>
