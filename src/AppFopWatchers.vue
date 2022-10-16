<template>
  <div>
    <FopWatchers />
  </div>
</template>

<script>
import FopWatchers from './components/FopWatchers.vue'

export default {
  name: 'AppFopWatchers',
  data() {
    return {
    }
  },
  components: {
    FopWatchers
  }
}
</script>

<style>
#AppFopWatchers{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
