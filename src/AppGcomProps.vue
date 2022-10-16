<template>
  <div>
    <CompositionPropsParent />
  </div>
</template>

<script>
import CompositionPropsParent from './components/GcomPropsParent.vue'

export default {
  name: 'AppGcomProps',
  data() {
    return {
    }
  },
  components: {
    CompositionPropsParent
  }
}
</script>

<style>
#AppGcomProps{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
