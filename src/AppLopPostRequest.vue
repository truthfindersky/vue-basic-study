<template>
  <div>
    <PostRequest />
  </div>
</template>

<script>
import PostRequest from './components/LopPostRequest.vue'

export default {
  name: 'AppLopPostRequest',
  data() {
    return {
    }
  },
  components: {
    PostRequest
  }
}
</script>

<style>
#AppLopPostRequest{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
