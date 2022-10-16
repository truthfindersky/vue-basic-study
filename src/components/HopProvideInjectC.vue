<template>
    <div>
        <h4>Component C</h4>
        <p>username: {{username}}</p>
    </div>
</template>

<script>
export default {
    app: 'HopProvideInjectC',
    inject:['username']
        
}
</script>

