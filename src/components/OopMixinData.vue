<template>
    <div>
        {{text}}
        <ul>
            <li v-for="car in cars" :key="car">
                {{car}}
            </li>
        </ul>
    </div>
</template>

<script>

import carMixin from '../mixins/data'

export default {
    name:'MixinData',
    data() {
        return {
            text: 'Moana',

        };
    },
    mixins: [carMixin]
};

</script>