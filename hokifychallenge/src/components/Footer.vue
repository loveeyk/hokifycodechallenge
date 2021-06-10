<template>
<div class="footer">
    <Icons />
</div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Icons from '../components/Icons.vue';

@Options({
    components: {
        Icons,
    },
})
export default class Footer extends Vue {

}
</script>

<style lang="scss">
@import 'src/assets/colors.scss';

.footer {
    position: fixed;
    bottom: 0;
    background: $color;
    color: $accent_colorLight;
    padding: 0.5rem;
    width: 100%;
}
</style>
