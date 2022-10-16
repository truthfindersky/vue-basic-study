<template>
  <div>
    <h1>Component Props</h1>

    <h4>Access from child</h4>
    <GopProps name="Moana" heroName="Superman" />
    <GopProps name="Laz" heroName="Batman" /><!-- use as many -->
    
    <h4>Access from this file</h4>
    <GopProps :name="name" :heroName="channel" />
  </div>
</template>

<script>
import GopProps from './components/GopProps.vue'

export default {
  name: 'AppGopProps',
  data() {
    return {
      name: 'Vishwas',
      channel: 'YouTube',
    }
  },
  components: {
    GopProps
  }
}
</script>

<style>
#AppGopProps{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
