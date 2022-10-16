<template>
    <h1>Composition API: Reactive & toRefs</h1>
   <!-- 1.  <h2>{{ sate.firstName }} {{ state.lastName }}</h2> -->
   <!-- 2.  <h2>{{ firstName }} {{ lastName }}</h2> -->
    <h2>{{ firstName }} {{ lastName }}</h2>
</template>

<script>
import { reactive, toRefs } from 'vue'
export default {
    name: 'CompositionReactive',
    setup() {
        const state = reactive({
            firstName: 'Bruce',
            lastName: 'Wayne',
        })

        setTimeout(() => {
            state.firstName = 'Clark'
            state.lastName = 'Kent'
            console.log(state)
        }, 2000)

        /*1
        return {
            state
        } 
        
        return{
            firstName = state.firstName,
            lastName = state.lastName
        }
        */

        return toRefs(state) //toRefs to change UI when it comes to an object
    },
}
</script>

<style scoped>

</style>