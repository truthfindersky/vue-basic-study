<template>
  <div>
    <GetRequest />
  </div>
</template>

<script>

import GetRequest from './components/LopGetRequest.vue'

export default {
  name: 'AppLopGetRequest',
  data() {
    return {
    }
  },
  components: {
    GetRequest
  }
}
</script>

<style>
#AppLopGetRequest {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
