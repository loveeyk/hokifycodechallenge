<template>
  <HeroVue path="../assets/logo_lovify.svg"/>
  <div class="home">  
   <h1>Willkommen auf Lovify.</h1>
     <!-- <img src="../assets/logo_lovify.svg" alt="logo" /> -->
  <button type="button">Contact me</button>

  </div>
</template>

<script lang="ts">
import HeroVue from '@/components/Hero.vue';
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
  
  button{
    background: #027f7e;
    color: white;
    padding: 1rem;
    border-radius: 5px;
    cursor: pointer;
    border: 1px solid transparent;
  }button:hover{
      background: #10b0af;
    }

}
</style>
