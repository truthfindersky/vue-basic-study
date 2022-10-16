<template>
    <div>
        <h1>Conditional Rendering</h1>
        <h4>1. v-if, v-else-if, v-else</h4>
        <p v-if="num === 0">The number is zero</p>
        <p v-else-if="num < 0">The number negative</p>
        <p v-else-if="num > 0">The number positive</p>
        <p v-else>Not a number</p>

        <h4>2. v-if="display"</h4>
        <div v-if="display">
            <p>Moana</p>
            <p>Dhaka</p>
            <p>Bangladesh</p>
        </div>

        <h4>3. v-show render in the dom if boolean value is false</h4>
        <div v-show="showElement">
            <p>Moana</p>
            <p>Dhaka</p>
            <p>Bangladesh</p>
        </div>

        <h4>4. List Rendering : Array</h4>
        <p v-for="name in names" :key="name">{{name}}</p>

        <h4>5. List Rendering : Array with index</h4>
        <p v-for="(name, index) in names" :key="name">{{index}} : {{name}}</p>

        <h4>6. List Rendering : Array and Object</h4>
        <p v-for="name in fullNames" :key="name.first">{{name.first}} {{name.last}}</p>

        <h4>7. List Rendering :Array of Arrays</h4>
        <div v-for="actor in actors" :key="actor.name">
            <p><b>{{actor.name}}</b></p>
            <p v-for="movie in actor.movies" :key="movie">{{movie}}</p>
        </div>

        <h4>8. Object</h4>
        <p v-for="value in myInfo" :key="value">{{value}}</p>

        <h4>9. Object, key, index</h4>
        <p v-for="(value, key, index) in myInfo" :key="value">{{index + 1}} : {{key}} : {{value}}</p>
    </div>

    <h4>10. Showing inside template</h4>
    <template v-for="name in names" :key="name">
        <p>{{name}}</p>
        <hr>
    </template>

    <div>
        <h4>11. Conditional List Rendering</h4>
        <template v-for="name in names" :key="name">
            <p v-if="name === 'Mamun'">{{name}}</p>
        </template>
    </div>

    <div>
        <h3>12. List Rendering </h3>
        <input type="text" v-model="newSkill.name" />
        <input type="text" v-model="newSkill.experience" />
        <button @click="addSkill">Add</button>
        <button @click="lastRemove(i)">Last Remove</button>
        <ul>
            <li v-for="(skill, i) in skills" :key="skill.name" @click="removeSkill(i)">
                <p>{{i +1}}. {{ skill.name }} ({{ skill.experience }})</p>
                <input type="text" placeholder="remark" @click.stop>
            </li>
        </ul>
    </div>

    <div>
        <h2>13. Template</h2>
        <span v-for="(name, index) in names" :key="index" class="item">
            {{ name }}
        </span>
    </div>

    <h4>14. List Rendering in table</h4>
    <table>
        <thead>
            <th>SL</th>
            <th>Name</th>
            <th>Roll</th>
            <th>Class</th>
            <th>Mobile</th>
        </thead>
        <tbody>
            <tr v-for="(value, i) in classInfo" :key="value.roll">
                <td>{{i+1}}</td>
                <td>{{value.name}}</td>
                <td>{{value.roll}}</td>
                <td>{{value.class}}</td>
                <td>{{value.mobile}}</td>
            </tr>
        </tbody>
    </table>

    <h4>15. Simple Loop</h4>
    <p v-for="i in 10" :key="i">{{i}}</p>

    <div>
        <h4>v-show</h4>
        <button @click="toggle">Show / Hide</button>
        <div v-show="show">
            <ul>
                <li v-for="(skill, i) in skills" :key="skill.name">
                    <p>
                        {{i + 1}}. {{ skill.name }} -
                        <span v-if="skill.experience < 4">Beginner</span>
                        <span v-else-if="skill.experience <= 6">Proficient</span>
                        <span v-else>Expert</span>
                    </p>
                </li>
            </ul>
            <br>
            <br>
            <br>
        </div>
    </div>

</template>

<script>

export default {
    name: 'BopConditional',
    data() {
        return {
            num: '1',
            display: true,
            showElement: true,
            names: ['Mamun', 'Moana', 'Laz'],
            fullNames: [
                { first: 'Abdullah', last: 'Al Mamun' },
                { first: 'Moana', last: 'Maherin' },
                { first: 'Sabiha', last: 'Sultana Laz' }
            ],
            actors: [
                {
                    name: 'Christian Bale',
                    movies: ['Batmap', 'The Prestige']
                },
                {
                    name: 'Di Caprio',
                    movies: ['Titanic', 'Inception']
                }
            ],
            myInfo: {
                name: 'Vishwas',
                channel: 'Codevolution',
                course: 'Vue 3'
            },
            skills: [
                { name: "HTML", experience: 2 },
                { name: "CSS", experience: 6 },
                { name: "JS", experience: 7 }
            ],
            newSkill: {
                name: '',
                experience: 0
            },
            classInfo: [
                { name: 'Moana', roll: 1, class: 'SSC', mobile: '01718305930' },
                { name: 'Mamun', roll: 2, class: 'HSC', mobile: '0171830000' },
                { name: 'Laz', roll: 3, class: 'HSC', mobile: '01718301010' }
            ],
            show: false
        }
    },
    methods: {
        addSkill() {
            this.skills.push(this.newSkill);
            this.newSkill = "";
        },
        removeSkill(i) {
            this.skills.splice(i, 1);
        },
        lastRemove(i) {
            this.skills.splice(-i, 1);
        },
        removeComma(index) {
            this.names.splice(index, 1)
        },
        toggle() {
            this.show = !this.show;
        }
    }
}
</script>

<style>
li {
    list-style: none;
}

table {
    width: 100%;
    border-collapse: collapse;
}

td,
th {
    border: 1px solid gray;
    padding: 5px;
}

.item+.item:before {
    content: ", ";
}
</style>