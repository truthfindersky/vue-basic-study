<template>
    <div>
       <h4>Component B</h4>
       <p>username: {{username}}</p>
        <ComponentC />
    </div>
</template>

<script>
import ComponentC from './HopProvideInjectC.vue';

export default {
    app: 'HopProvideInjectB',
    inject: ['username'],
    components: {
        ComponentC
        }
        
    }
</script>