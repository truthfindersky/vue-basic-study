<template>
  <div>
    <button @click="showPopup = true">Show popup</button>
    <CopEventPopup v-show="showPopup" @close="closePopup" />
  </div>
</template>

<script>
import CopEventPopup from './components/CopEventPopup.vue'

export default {
  name: 'AppCopEventPopup',
  data() {
    return {
      showPopup: false
    }
  },
  components: {
    CopEventPopup
  },
  methods: {
    closePopup(name) {
      this.showPopup = false
      console.log('name', name)
    }
  }
}
</script>

<style>
#AppCopEventPopup{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
