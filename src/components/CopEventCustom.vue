<template>
    <div>
        <h1>v-model, custom event</h1>
        <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" />
    </div>
</template>

<script>
export default {
    name: 'CopEventCustom',
    props: {
        modelValue: String //hold the input value 
    }
}
</script>

<!-- install vue dev tools (chrome extension) -->