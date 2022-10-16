<template>
  <div>
    <MopHooksParent />
  </div>
</template>

<script>
import MopHooksParent from './components/MopHooksParent.vue'

export default {
  name: 'AppMopHooks',
  data() {
    return {
    }
  },
  components: {
    MopHooksParent
  }
}
</script>

<style>
#AppMopHooks{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
