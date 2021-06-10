<template>
    <Navbar />
    <Footer />
  <router-view/>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue'

@Options({
  components: {
    Navbar,
    Footer,
  },
})

export default class App extends Vue {}

</script>
<style lang="scss">

</style>
