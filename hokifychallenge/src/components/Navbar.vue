<template>
  <ul class="navbar">
      <li v-for="(link,index) in links" :key="index">
          <router-link :to="link.path">{{link.name}}</router-link>
    </li>
</ul>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'

export default class Navbar extends Vue {

links:any = [{name: "Home", path:"/"}, {name: "Contact", path: "/contact"}, {name: "LoginForm", path: "/login"}];

}
</script>

<style lang="scss">

.navbar{
    background: #10b0af;
    color: white;
    list-style: none;
    li{ 
        display: inline-block;
        padding: 1rem;
        a{
        color: white;
        text-decoration: none;
        }
    }
}
</style>