<template>
  <div>
    <CopBinding />
  </div>
</template>

<script>
import CopBinding from './components/CopBinding.vue'

export default {
  name: 'AppCopBinding',
  data() {
    return {
    }
  },
  components: {
    CopBinding
  }
}
</script>

<style>
#AppCopBinding {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
