<template>
  <div>
    <CompositionApi />
  </div>
</template>

<script>
import CompositionApi from './components/PcomApi.vue'

export default {
  name: 'AppPcomApi',
  data() {
    return {
    }
  },
  components: {
    CompositionApi
  }
}
</script>

<style>
#AppPcomApi{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
