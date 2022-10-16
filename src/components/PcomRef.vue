<template>
    <h1>Composition API: ref</h1>
    <h2>{{ name }}</h2>
</template>

<script>

import { ref } from 'vue'

export default {
    name: 'CompositionRef',
    setup() {
        const name = ref('Vishwas') //without ref(), name won't change in the ui though it will change inside dom

        setTimeout(() => {
            name.value = 'Codevolution'
            console.log(name.value)
        }, 2000)

        return {
            name,
        }
    },
}
</script>

<style scoped>

</style>