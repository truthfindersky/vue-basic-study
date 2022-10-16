<template>
    <div class="container ">
        <h1>Child - Custom Events - Parent </h1>
        <div class="col d-flex justify-content-center">
            <div>
                <h4>Popup example</h4>
                <input type="text" v-model="name"><br><br>
                <button @click="$emit('close', name)">Colse Popup</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    app: 'CopEventPopup',
    data() {
        return {
            name: ''
        }
    },
    /* Validating Emitted Events */
    emits: {
        close: (name) => {
            if (!name) {
                return false
            } else {
                return true
            }
        }
    }
}
</script>

