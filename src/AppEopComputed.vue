<template>
  <div>
    <EopComputed />
  </div>
</template>

<script>
import EopComputed from './components/EopComputed.vue'

export default {
  name: 'AppEopComputed',
  data() {
    return {
    }
  },
  components: {
    EopComputed
  }
}
</script>

<style>
#AppEopComputed{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
