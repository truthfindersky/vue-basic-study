<template>
<!-- id="my-article" non prop attributes, it needs to be placed inside div --> 
  <div><GopPropsValidation id="my-article" title="Moana" :likes="10" :isPublished="true" /></div>
</template>

<script>
import GopPropsValidation from './components/GopPropsValidation.vue'

export default {
  name: 'AppGopPropsValidation',
  data() {
    return {
      name: 'Vishwas',
      channel: 'YouTube',
      showPopup: false
    }
  },
  components: {
    GopPropsValidation
  }
}
</script>

<style>
#AppGopPropsValidation{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
