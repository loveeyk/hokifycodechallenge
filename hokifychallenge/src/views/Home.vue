<template>
  <div class="home">  
    <span>Homeview</span>  
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {
  },
})
export default class Home extends Vue {}
</script>

<style lang="scss">
.home{
display: flex;
justify-content: center;
align-items:center;
height: 100vh;
  span{
    font-size: 20vw;
  }
}
</style>
