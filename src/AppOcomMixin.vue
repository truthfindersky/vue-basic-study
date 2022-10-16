<template>
    <div>
        <OcomMixinCounter />
        <OcomMixinHover/>
    </div>
</template>

<script>
import OcomMixinCounter from './components/OcomMixinCounter.vue'
import OcomMixinHover from './components/OcomMixinHover.vue'
export default {
    name: 'AppOcomMixin',
    data() {
        return {
        }
    },
    components: {
        OcomMixinCounter,
        OcomMixinHover
    }
}
</script>

<style>
#AppOcomMixin {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 10px;
}
</style>
