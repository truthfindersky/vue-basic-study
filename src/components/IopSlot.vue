<template>

    <!-- 1 -->
    <div>
        <slot name="listitem"></slot>
    </div>
    <br />

    <!-- 2 -->
    <div>
        <slot name="listname">
            <h4 v-for="name in names" :key="name.firstName">
                {{name.firstName}} {{name.lastName}}
            </h4>
        </slot>
    </div>
    <br />

    <!-- 3 -->
    <div>
        <h6 v-for="name in names" :key="name.firstName">
            <slot name="anotherList" :firstName="name.firstName" :lastName="name.lastName"></slot>
        </h6>
    </div>

</template>

<script>
export default {
    name: 'SlotProps',
    data() {
        return {
            names: [
                {
                    firstName: 'Moana',
                    lastName: 'Maherin'
                },
                {
                    firstName: 'Abdullah',
                    lastName: 'Al Mamun'
                },
                {
                    firstName: 'Sabiha',
                    lastName: 'Sultana Laz'
                }
            ],
        }
    }
}
</script>

<style scoped>

</style>


