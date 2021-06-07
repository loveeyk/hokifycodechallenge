<template>
<div>

  <ul>
      <li v-for="(link,index) in links" :key="index">
          {{link}}
          </li>
</ul>
</div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
export default class Navbar extends Vue {

links:any = [""];

}
</script>

<style>

</style>