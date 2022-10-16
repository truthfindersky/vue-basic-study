<template>
    <div>
        <button @click="increamentCount">Clicked {{count}} Times</button>
    </div>
</template>

<script>

import CounterMixin from '../mixins/counter'

export default {
    name: 'MixinCounter',
    mixins: [CounterMixin]
    
}
</script>

<style lang="scss" scoped>

</style>