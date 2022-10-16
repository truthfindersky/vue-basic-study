<template>
    <div>
        <p>{{name}} {{heroName}}</p>
    </div>
</template>

<script>
export default {
    name: 'VueProps',
    props: ['name', 'heroName']
}
</script>