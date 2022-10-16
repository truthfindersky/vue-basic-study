<template>
    <div>
        <h1>Template Refs</h1>
        <input type="text" ref="inputRef">
        <GetRequest ref="PostListRef" />
    </div>
</template>

<script>

import GetRequest from './LopGetRequest.vue'

export default {
    name: 'TemplateRef',
    mounted() {
        console.log(this.$refs.PostListRef)
        this.$refs.inputRef.focus()
    },
    components: {
        GetRequest
    }
}
</script>