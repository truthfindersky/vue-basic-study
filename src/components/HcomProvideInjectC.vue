<template>
    <h2>Child Component C</h2>

    <!-- 1 -->
    <h3>1.2 Child Component C Option API: username - {{ userName }}</h3>

    <!-- 2 -->
    <h3>2. Child Component C composition API: username - {{ childUserName }}</h3>

    <!-- 3  -->
    <h3>3. Child Component C count - {{ childCount }}</h3>
    <button @click="incrementCount">Increment count from child</button>

    <!-- 4 -->
    <h3>4. Child Component C hero - {{ firstName }} {{ lastName }}</h3>
    
</template>

<script>
/* 2 */
import { inject, toRefs } from 'vue'
export default {
    name: 'HcomProvideInjectC',
    setup() {
        /* 2 */
        const childUserName = inject('c_userName', 'Default username')
        /* 3 */
        const childCount = inject('c_count', 0)
        const incrementCount = inject('incrementCount')
        /* 4 */
        const childHero = inject('c_hero', {})//
        

        return {
            /* 2 */
            childUserName,
            /* 3 */
            childCount,
            incrementCount,
            /* 4 */
            ...toRefs(childHero)
        }
    },
    /* 1 */
    inject: ['userName'],
}
</script>

<style scoped>

</style>