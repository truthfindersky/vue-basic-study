<template>
  <div>
    <CcomEvent />
  </div>
</template>

<script>
import CcomEvent from './components/CcomEvent.vue'


export default {
  name: 'AppCcomEvent',
  data() {
    return {
    }
  },
  components: {
    CcomEvent,
  }
}
</script>

<style>
#AppCcomEvent{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
