<template>
  <div>
    <CopMethods />
  </div>
</template>

<script>
import CopMethods from './components/CopEvents.vue'

export default {
  name: 'AppCopEvents',
  data() {
    return {
    }
  },
  components: {
    CopMethods
  }
}
</script>

<style>
#AppCopEvents{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
