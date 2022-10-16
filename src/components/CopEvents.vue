<template>
    <div>
        <h1>Events</h1>
        <p>{{1+2+7}}</p>
        <p>Method: {{add(2,5,3)}}</p>
        <p>Multiply: {{multiply(10)}}</p>
        <p>Multiply: {{multiply(baseValue)}}</p>

        <h4>Event Handling: Example 1</h4>
        <p>{{name}}</p>
        <button @click="name = 'Mamma'">Click</button>
        <button @mouseover="name = 'Muan'">Mouseover</button>
        <button @click="updateName">Change Name</button>

        <h4>Event Handling: Example 2</h4>
        <p>{{count}}</p>
        <button @click="count += 1">Increment</button>
        <button @click="count -= 1">Decrement</button>

        <h4>Event Handling: Example 3</h4>
        <p>{{counting}}</p>
        <button @click="increment(10)">Increment</button>
        <button @click="decrement(10)">Decrement</button>

         <h4>Event Handling: Example 4</h4>
         <p>{{title}}</p>
        <button @click="changeTitle($event), incrementing(1, $event)">Change Name</button>
        <p>{{counts}}</p>
        <button @click="incrementing(1, $event)">Increment</button>

        <form @submit.prevent="handleFormSubmit">
            <h3>Enter your Country</h3>
            <input type="text" @keyup.enter="handleKeyup" />
            <p>Welcome {{country}}!</p>
            <button type="submit">OK</button>
        </form>
    </div>
</template>


<script>

export default {
    name: 'CopEvents',
    data() {
        return {
            baseMultiplier: 5,
            baseValue: 2,
            name: 'Moana',
            count: 0,
            counting:0,
            title: 'Vue',
            counts: 0,
            country:''
        }
    },
    /* Use regular function in methods in stead of arrow function */
    methods:{
        add(a,b,c) {
            return a + b + c;
        },
        multiply(num) {
            return num * this.baseMultiplier;
        },
        updateName() {
            this.name = 'Mayan';  
        },
        increment(num){
            this.counting += num;
        },
        decrement(num) {
            this.counting -= num;
        },
        changeTitle(event) {
            this.title = 'Vue 3'
            console.log('Event', event);  
        },
        incrementing(num, event) {
            this.counts += num;
            console.log('Event', event);
        },
        handleKeyup(e) {
            this.country = e.target.value;
        },

        handleFormSubmit() {
            console.log("Form submitted!");
        }
    }
}
</script>