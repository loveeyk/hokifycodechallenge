<template>
  <HeroVue path="../assets/logo_lovify.svg"/>
  <div class="home">  
   <h1>{{msg}}</h1>
     <!-- <img src="../assets/logo_lovify.svg" alt="logo" /> -->
  <a href="contact">Kontaktaufnahme</a>

  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {
  },
})
export default class Home extends Vue {
msg = "Willkommen bei Lovify"
   
   
}
</script>

<style lang="scss">
@import 'src/assets/colors.scss';
.home{
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  align-items: center;
  height: 70vh;
  a{
    padding: 1rem;
    background: $color;
    color: $accent_colorLight;
    text-decoration: none;
    border: 1px solid $highlight_light;
    box-shadow: 1px 2px 8px $color_light;
    border-radius: 5px;
  }
}
</style>
