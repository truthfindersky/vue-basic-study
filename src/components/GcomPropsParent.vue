<template>
    <div>
        <input type="text" placeholder="First Name" v-model="firstName" />
        <input type="text" placeholder="Last Name" v-model="lastName" />
    </div>
    <CompositionPropsChild :firstName="firstName" :lastName="lastName" @callHeroes="callHeroes" />
</template>

<script>
import { ref } from 'vue'
import CompositionPropsChild from './GcomPropsChild.vue'
export default {
    name: 'CompositionPropsParent',
    components: {
        CompositionPropsChild,
    },
    setup() {
        const firstName = ref('')
        const lastName = ref('')

        function callHeroes(hero) {
            alert(`Calling ${hero}`)
        }

        return {
            firstName,
            lastName,
            callHeroes,
        }
    },
}
</script>

<style scoped>

</style>