<template>
    <div>
        <h2 @mouseover="increamentCount">Hovered {{count}} Times</h2>
    </div>
</template>

<script>

import CounterMixin from '../mixins/counter'

export default {
    name: 'MixinHover',
    mixins: [CounterMixin]
}
</script>

<style lang="scss" scoped>

</style>