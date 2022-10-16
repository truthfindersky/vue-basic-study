<template>
    <div> 
        
        <h1>Lifecycle Hooks: Parent</h1>
        <button @click="showChild = !showChild">Toggle Child</button>
        <MopHooksChild v-if="showChild" />
    </div>
</template>

<script>

import MopHooksChild from './MopHooksChild.vue';

export default {
    name: 'MopHooksParent',
    data() {
        return {
            showChild:true
        }
    },
    components: {
        MopHooksChild
    },
    beforeCreate() {
        console.log('Parent beforeCreate()')
    },
    created() {
        console.log('Parent created()')
    },
    beforeMount() {
        console.log('Parent beforeMount()')
    },
    mounted() {
        console.log('Parent mounted()')
    },
    beforeUpdate() {
        console.log('Parent beforeUpdate()')
    },
    updated() {
        console.log('Parent updated()')
    },
    beforeUnmount() {
        console.log('Parent beforeUnmount()')
    },
    unmounted() {
        console.log('Parent unmounted()')
    }

}
</script>

