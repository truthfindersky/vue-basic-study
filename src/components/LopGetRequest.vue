<template>
    <div>
        <h1>HTTP Get Request</h1>
        <!-- request to api to fetch data -->
      <button @click="getPosts">Load Post</button>
        <h3 v-if="errorMsg">{{errorMsg}}</h3>
        <div v-for="post in posts" :key="post.id">
            <h4>{{post.id}} {{post.title}}</h4>
            <p>{{post.body}}</p>
            <hr>
        </div>
    </div>
</template>

<script>

import axios from 'axios'

export default {
    name: 'GetRequest',
    /* created() {
      this.getPosts()  
    }, */
    data() {
        return {
            posts: [],
            errorMsg:''
        }
    },
    methods: {
        getPosts() {
            axios.get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => {
                    console.log(response.data)
                    this.posts = response.data
                })
                .catch((error) => {
                    console.log(error)
                this.errorMsg = 'Error retrieving data'
            })
        }
    }
}
</script>

<style lang="scss" scoped>

</style>