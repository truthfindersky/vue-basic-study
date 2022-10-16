<template>
  <div class="container">
    <div class="row">
      <MixinCounter />
      <MixinHover />
      <MixinData />
    </div>
  </div>
</template>

<script>
import MixinCounter from './components/OopMixinCounter.vue'
import MixinHover from './components/OopMixinHover.vue'
import MixinData from './components/OopMixinData.vue'
export default {
  name: 'AppOopMixin',
  data() {
    return {
    }
  },
  components: {
    MixinCounter,
    MixinHover,
    MixinData
  }
}
</script>

<style>
#AppOopMixin{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 10px;
}
</style>