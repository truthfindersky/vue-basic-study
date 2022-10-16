<template>
    <div>
        <h1>Composition API: Computed Properties</h1>
        <!-- Options API -->
        <h2>Options API</h2>
        <input type="text" placeholder="First Name" v-model="fName" /><br/><br/>
        <input type="text" placeholder="Last Name" v-model="lName" /><br /><br />
        <p>Options Fullname is {{ fullName }}</p><br /><br />

        <!-- ref -->
        <h2>Composition API: ref</h2>
        <input type="text" placeholder="First Name" v-model="refFirstName" /><br /><br />
        <input type="text" placeholder="Last Name" v-model="refLastName" /><br /><br />
        <p>ref Fullname is {{ refFullName }}</p><br /><br />

        <!-- reactive -->
        <h2>Composition API: reactive</h2>
        <input type="text" placeholder="First Name" v-model="reactiveFirstName" /><br /><br />
        <input type="text" placeholder="Last Name" v-model="reactiveLastName" /><br /><br />
        <p>reactive Fullname is {{ reactiveFullName }}</p>
    </div>
</template>

<script>
import { ref, reactive, toRefs, computed } from 'vue'
export default {
    name: 'EcomComputed',
    setup() {
        const refFirstName = ref('')
        const refLastName = ref('')

        const state = reactive({
            reactiveFirstName: '',
            reactiveLastName: '',
        })

        const refFullName = computed(function () {
            return `${refFirstName.value} ${refLastName.value}`
        })

        const reactiveFullName = computed(function () {
            return `${state.reactiveFirstName} ${state.reactiveLastName}`
        })

        return {
            refFirstName,
            refLastName,
            refFullName,
            ...toRefs(state),
            reactiveFullName,
        }
    },
    data() {
        return {
            fName: '',
            lName: '',
        }
    },
    computed: {
        fullName() {
            return `${this.fName} ${this.lName}`
        },
    },
}
</script>

<style scoped>

</style>