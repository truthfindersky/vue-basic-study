<template>
  <div>
    <CompositionTemplateRef />
  </div>
</template>

<script>
import CompositionTemplateRef from './components/NcomTemplateRef.vue'

export default {
  name: 'AppNcomTemplateRef',
  data() {
    return {
    }
  },
  components: {
    CompositionTemplateRef
  }
}
</script>

<style>
#AppNcomTemplateRef{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
