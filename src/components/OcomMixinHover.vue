<template>
    <div>
        <h1>Hover Counter</h1>
        <h2 @mouseover="incrementCount">Hovered {{ count }} times</h2>
    </div>
</template>

<script>
import useCounter from '../mixins/useCounter'
export default {
    name: 'CompositionMixinHover',
    setup() {
        const { count, incrementCount } = useCounter()
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