<template>
  <div>
    <FcomWatchers />
  </div>
</template>

<script>
import FcomWatchers from './components/FcomWatchers.vue'

export default {
  name: 'AppFcomWatchers',
  data() {
    return {
    }
  },
  components: {
    FcomWatchers
  }
}
</script>

<style>
#AppFcomWatchers{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
