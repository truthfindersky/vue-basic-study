<template>
  <div>
    <CompositionVmodel />
  </div>
</template>

<script>
import CompositionVmodel from './components/PcomVmodel.vue'

export default {
  name: 'AppPcomVmodel',
  data() {
    return {
    }
  },
  components: {
    CompositionVmodel
  }
}
</script>

<style>
#AppPcomVmodel{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
