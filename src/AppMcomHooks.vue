<template>
  <div>
    <McomHooks />
  </div>
</template>

<script>
import McomHooks from './components/McomHooks.vue'

export default {
  name: 'AppMcomHooks',
  data() {
    return {
    }
  },
  components: {
    McomHooks
  }
}
</script>

<style>
#AppMcomHooks {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
