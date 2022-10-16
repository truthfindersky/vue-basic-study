<template>
  <div>
    <EcomComputed />
  </div>
</template>

<script>
import EcomComputed from './components/EcomComputed.vue'

export default {
  name: 'AppEcomComputed',
  data() {
    return {
    }
  },
  components: {
    EcomComputed
  }
}
</script>

<style>
#AppEcomComputed{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
