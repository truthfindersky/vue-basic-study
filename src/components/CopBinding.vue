<template>
    <div class="container ">
        <div>
            <h1>Two Way Bindings</h1>
            <h3>Enter a number</h3>
            <input v-model.number="num" type="text" />
            <br />
            <button @click="getDouble">Get Double</button>
            <button @click="getSquare">Get Square</button>
            <button @click="addTen">Add 10</button>
            <button @click="reset">Reset</button>
            <hr />

            <label>Entered Number: </label> {{ num }}
            <br />
            <label>Result:</label> {{ result }}
        </div>

        <div>
            <h2>Class Binding</h2>
            <button
                class="button"
                :class="{active: activeClass == 'red'}"
                @click="setClass('red')">
                Red
            </button>
            <button
                class="button"
                :class="{active: activeClass == 'green'}"
                @click="setClass('green')">
                Green
            </button>
            <button
                class="button"
                :class="{active: activeClass == 'blue'}"
                @click="setClass('blue')">
                Blue
            </button>

            <button :class="['button', 'active']">Always Active</button>
            <br />

            <div :class="activeClass"></div>
        </div>
    </div>
</template>

<script>
export default {
    app: 'CopBinding',
    data() {
        return {
            num: "",
            result: "",
            activeClass: "red"
        }
    },
    methods: {
        getDouble() {
            this.result = this.num * 2;
        },

        getSquare() {
            this.result = this.num * this.num;
        },

        addTen() {
            this.result = this.num + 10;
        },

        reset() {
            this.num = "";
            this.result = "";
        },
        setClass(className) {
            this.activeClass = className;
        }
    }
}
</script>

<style>
.button {
    padding: 5px 11px;
    margin: 5px;
}

.active {
    background-color: rgb(3, 78, 97);
    color: #fff;
    border: 1px solid rgb(3, 78, 97);
}

.red {
    width: 100px;
    height: 50px;
    background-color: red;
}

.green {
    width: 100px;
    height: 50px;
    background-color: green;
}

.blue {
    width: 100px;
    height: 50px;
    background-color: blue;
}
</style>
