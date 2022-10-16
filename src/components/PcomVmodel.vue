<template>
    <div>
        <h1>Composition API and V-Model</h1>

        <h4>Optional Method</h4>
        <!-- Options API -->
        <input type="text" placeholder="First Name" v-model="fName" /><br><br>
        <input type="text" placeholder="Last Name" v-model="lName" /><br><br>

        <br>
        <h4>Using ref</h4>
        <!-- ref -->
        <input type="text" placeholder="Hero Name" v-model="heroName" /><br><br>

        <h4>Using reactive</h4>
        <!-- reactive -->
        <input type="text" placeholder="First Name" v-model="firstName" /><br><br>
        <input type="text" placeholder="Last Name" v-model="lastName" /><br><br>
    </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue'
export default {
    name: 'CompositionVmodel',
    setup() {
        const heroName = ref('')
        const state = reactive({
            firstName: '',
            lastName: '',
        })

        return {
            heroName,
            ...toRefs(state),
        }
    },
    data() {
        return {
            fName: '',
            lName: '',
        }
    },
}
</script>

<style scoped>

</style>