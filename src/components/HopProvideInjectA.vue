<template>
    <div>
        <h4>Component A, username not injected</h4>
        <p>username: {{username}}</p>
        <HopProvideInjectB /> 
    </div>
</template>

<script>
import HopProvideInjectB from './HopProvideInjectB.vue';

export default {
    app: 'HopProvideInjectA',
    data() {
        return {

        }
    },
    components: {
        HopProvideInjectB
    }

}
</script>