<template>
  <div>
    <BopConditional />
  </div>
</template>

<script>
import BopConditional from './components/BopConditional.vue'

export default {
  name: 'AppBopConditional',
  data() {
    return {
    }
  },
  components: {
    BopConditional
  }
}
</script>

<style>
#AppBopConditional{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
