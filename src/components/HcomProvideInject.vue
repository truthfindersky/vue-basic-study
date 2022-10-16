<template>
    <h1>Provide Inject Option API</h1>
    <!-- 1 -->
    <h3>1.1 Parent component username: {{ name }}</h3>

    <!-- 3 -->
    <h3>3 Parent component {{ count }}</h3>
    <button @click="incrementCount">Increment count</button>
    <h3>4 Parent component {{ firstName }} {{ lastName }}</h3>
   
    <HcomProvideInjectA />
</template>

<script>

/* 2 */
import { provide, ref, reactive, toRefs } from 'vue'
import HcomProvideInjectA from './HcomProvideInjectA.vue'
export default {
    components: { HcomProvideInjectA },
    name: 'HcomProvideInject',
    setup() {

        /* 2 */
        provide('c_userName', 'Codevolution')

        /* 3 */
        const count = ref(0)
        function incrementCount() {
            count.value++
        }
        provide('c_count', count)
        provide('incrementCount', incrementCount)

        /* 4 */
        const state = reactive({
            firstName: 'Bruce',
            lastName: 'Wayne',
        })
        provide('c_hero', state)
        
        return {
            count,
            incrementCount,
            ...toRefs(state),
        }
    },
    /* 1 */
    data() {
        return {
            name: 'Vishwas',
        }
    },
    /* 1. provide helps to send data to child without props and also to show username in this parent component */
    provide() {
        return {
            userName: this.name,
        }
    },
}
</script>

<style scoped>

</style>