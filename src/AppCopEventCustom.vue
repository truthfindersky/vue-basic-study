<template>
  <div>
    <CopEventCustom v-model="name"/>

  </div>
</template>

<script>
import CopEventCustom from './components/CopEventCustom.vue'

export default {
  name: 'AppCopEventCustom',
  data() {
    return {
      name:''
    }
  },
  components: {
    CopEventCustom
  }
}
</script>

<style>
#AppCopEventCustom{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
