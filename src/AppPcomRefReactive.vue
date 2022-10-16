<template>
  <div>
    <CompositionRef />
    <CompositionReactive />
  </div>
</template>

<script>
import CompositionRef from './components/PcomRef.vue'

import CompositionReactive from './components/PcomReactive.vue'

export default {
  name: 'AppPcomRefReactive',
  data() {
    return {
    }
  },
  components: {
    CompositionRef,
    CompositionReactive
  }
}
</script>

<style>
#AppPcomRefReactive{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
