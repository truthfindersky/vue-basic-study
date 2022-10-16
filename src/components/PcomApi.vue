<template>
    <div>
        <h1>Composition API: ref and reactive</h1>
        <p>Options: {{o_firstName}}</p>
        <p>Options: {{o_firstName}} {{o_lastName}} a.k.a {{o_heroName}}</p>
        
        <p>Composition-ref: {{c_firstName}}</p>
        <p>Composition-ref: {{greet}}</p>
        
        <p>Composition-ref: {{c_firstName}} {{c_lastName}} a.k.a {{c_heroName}}</p>
        <p>Composition-ref: {{greetHero}}</p>
        
        <p>Composition-State: {{state.firstName}} {{state.lastName}} a.k.a {{state.heroName}}</p>
        <p>Composition-State: {{reactiveGreetHero}}</p>
    </div>
</template>

<script>

import { ref, reactive } from 'vue';
    
    export default {
    name: 'CompositionApi',
    //composition api setup()
    setup() {

        //ref
        const c_firstName = ref('Clark')
        const c_lastName = ref('Kent')
        const c_heroName = ref('Superman') 

        const greet = `Hello ${c_firstName.value}`
        const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`

        //reactive
        const state = reactive({
            firstName: 'Princess',
            lastName: 'Diana',
            heroName: 'Wonder Woman'
        })

        const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`

        /* use ref to primitive values like string, number, value etc
        use reactive when needs an object, you can store username, email and other things into profile with reactive, object
        const isLoggedIn = ref(false)
        const isLoggedInReactive = ({
            value: false
        }) */

        return {
            //c_firstName: c_firstName
            c_firstName,
            c_lastName,
            c_heroName,
            greet,
            greetHero,
            state,
            reactiveGreetHero
        }
    },
    //optional api
    data() {
        return {
            o_firstName: 'Bruce',
            o_lastName: 'Wayne',
            o_heroName: 'Batman'
        }
    }
    }
</script>

<style lang="scss" scoped>

</style>