<template>
<ul class="navbar">
    <li><a href="/"><img src="../assets/logo_lovify.svg" /></a></li>
    <li v-for="(link,index) in links" :key="index">
        <router-link :to="link.path">{{link.name}}</router-link>
    </li>
   
</ul>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Icons from '../components/Icons.vue';

@Options({
  components: {
    Icons,
  },
})
export default class Navbar extends Vue {
    links: any = [{ name: "Home", path: "/" }, { name: "Kontakt", path: "/contact" }];
}
</script>

<style lang="scss">
@import 'src/assets/colors.scss';
.navbar {
    position:absolute;
    display: flex;
    background: $color;
    color: $accent_colorLight;
    list-style: none;
    box-shadow: 1px 3px 1px $shadow;
    padding: 0.2rem;
    width: 100%;
    overflow: hidden;
    flex-wrap: wrap;
    img {
        width: 80px;
    }
    li {
        display: inline-flex;
        align-items: center;
        padding: 0 1rem;
    }
    a {
        color: $accent_colorLight;
        text-decoration: none;
    }
}
</style>
