<template>
<ul class="navbar">
    <li><a href="/"><img src="../assets/logo_lovify.svg" /></a></li>
    <li v-for="(link,index) in links" :key="index">
        <router-link :to="link.path">{{link.name}}</router-link>
    </li>
</ul>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'

export default class Navbar extends Vue {
    links: any = [{ name: "Home", path: "/" }, { name: "Kontakt", path: "/contact" }];
}
</script>

<style lang="scss">
@import 'src/assets/colors.scss';
.navbar {
    display: flex;
    background: $color;
    color: $accent_colorLight;
    list-style: none;
    box-shadow: 1px 3px 15px $highlight;
    padding: 0.5rem;
    width: 100%;
    overflow: hidden;
    img {
        width: 100px;
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
