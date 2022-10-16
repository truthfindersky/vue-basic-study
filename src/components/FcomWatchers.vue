<template>
    <div>
        <h1>Composition API: Watchers</h1>
        <!-- 1 -->
        <h2>Option API</h2>
        <input type="text" placeholder="name" v-model="name">

        <!-- 2 -->
        <h2>Composition API: ref</h2>
        <input type="text" placeholder="Ref First Name" v-model="firstName">
        <input type="text" placeholder="Ref Last Name" v-model="lastName">

        <!-- 3 -->
        <h2>Composition API: reactive</h2>
        <input type="text" placeholder="Reactive First Name" v-model="fName">
        <input type="text" placeholder="Reactive Last Name" v-model="lName"><br><br>
        <!-- 4 -->
        <input type="text" placeholder="Reactive Hero Name" v-model="options.heroName"><!-- deep watch -->
    </div>
</template>

<script>


import { ref, reactive, toRefs, watch } from 'vue'
import _ from 'lodash' //npm install lodash

export default {
    name: 'FcomWatchers',
    setup() {

        //2. ref 
        const firstName = ref('')
        const lastName = ref('')

        /* 2 */
        /*  watch(firstName, (newValue, oldValue) => {
            console.log('old value', oldValue)
            console.log('new value', newValue)
        }) */ 

        /* 2 */
        //watch also accepts array of data sources, 
          watch([firstName, lastName], (newValues, oldValues) => {
            console.log('First Name old value', oldValues[0])
            console.log('First Name new value', newValues[0])
            console.log('Last Name old value', oldValues[1])
            console.log('Last Name new value', newValues[1])
        }, {
            immediate:true
        })  

        //3. reactive
        const state = reactive({
            fName: '',
            lName: '',
            /* 4 */
            options: {
                heroName:''
            }
        })

        //3. not favourable when many more properties
        /*
         watch(() => {
            return {...state}
        }, function(newValue, oldValue) {
            console.log('FName old value', oldValue.fName)
            console.log('FName new value', newValue.fName)
            console.log('LName old value', oldValue.lName)
            console.log('LName new value', newValue.lName)
        })  */

        //3. build watch individually and it needs a getter function
         watch(
            () => state.fName,
            (newValue, oldValue) => {
            console.log('FName old value', oldValue)
            console.log('FName new value', newValue)
            })   

        /* 4 */
        watch(
            () => _.cloneDeep(state.options),
            (newValue, oldValue) => {
            console.log('FName old value', oldValue)
            console.log('FName new value', newValue)
            }, {
            deep:true
        })
        
        return {
            firstName,
            lastName,
            ...toRefs(state)
        }
    },
    /* 1 */
    data() {
        return {
            name: '',
        }
    },
    /* 1 */
    watch: {
        name(newValue, oldValue) {
            console.log('old value', oldValue)
            console.log('new value', newValue)
        }
    }
}
</script>

<style scoped>

</style>