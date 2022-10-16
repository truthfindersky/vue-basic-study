<template>
    <div>
        <button @click="incrementCount">Clicked {{ count }} times</button>
    </div>
</template>

<script>
import useCounter from '../mixins/useCounter'
export default {
    name: 'OcomMixinCounter',
    setup() {
        const { count, incrementCount } = useCounter(100, 10)
        return {
            count,
            incrementCount,
        }
    },
    // mixins: [CounterMixin],
}
</script>

<style scoped>

</style>