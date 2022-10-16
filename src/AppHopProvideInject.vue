<template>
  <h1>Option API: Provide Inject</h1>
  <p>App component username: {{name}}</p>
  <div><HopProvideInjectA/></div>
</template>

<script>
import HopProvideInjectA from './components/HopProvideInjectA.vue'

export default {
  name: 'AppHopProvideInject',
  data() {
    return {
      name: 'Vishwas'
    }
  },
  components: {
    HopProvideInjectA
  },
  provide(){
    return {
      username: this.name
    }
  }
}
</script>

<style>
#AppHopProvideInject{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
