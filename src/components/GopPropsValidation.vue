<template>
    <div>
        <h1>Props Validation</h1>
        <p v-bind="$attrs">Title: {{title}}</p><!-- Non Prop Attributes: v-bind="$attrs" -->
        <p>Likes: {{likes}}</p>
        <p>Publish: {{isPublished ? 'Yes' : 'No' }}</p>
    </div>
</template>

<script>
    export default {
    name: 'PropsValidation',
        props: {
            title: {
                type: String,
                required: true,
                default: 'Article Default Title'
            },
            likes: Number,
            isPublished: Boolean
        },
        inheritAttrs: false //non prop attribute to be applied to the root (div) element
    }
</script>

