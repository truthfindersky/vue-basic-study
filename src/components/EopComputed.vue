<template>

    <h4>Computed Properties for App performance</h4>
    <div>
        <h4>Method</h4>
        <ul>
            <li v-for="(skill, i) in skills" :key="skill.name" @click="removeSkill(i)">
                <p>{{i +1}}. {{ skill.name }} ({{ skill.experience }})</p>
            </li>
        </ul>
    </div>

    <input type="text" placeholder="Write your review" v-model="review" />
    
   <!--  <p>Total count: {{totalCount()}}</p> --><!-- method countes every time when value change -->
    <p>Total count: {{totalCount1}}</p> <!-- computed properties do not use aurguments/property -->

    <div>
        <h2>Computed</h2>
        <ul>
            <li
                v-for="(skill, i) in experiencedSkills"
                :key="skill.name"
                @click="removeSkill(i)">
                <p>{{ skill.name }} - {{ skill.experience }}</p>
            </li>
        </ul>
    </div>
</template>

<script>

export default {
    name: 'ComputedProperties',
    data() {
        return {
            review: '',
            skills: [
                { name: "HTML", experience: 5 },
                { name: "CSS", experience: 10 },
                { name: "JS", experience: 5 },
                { name: "Java", experience: 4 },
                { name: "php", experience: 15 },
                { name: "node js", experience: 15 },
                { name: "python", experience: 2 },
                { name: "go", experience: 1 }
            ]
        }
    },
    methods: {
        removeSkill(i) {
            this.skills.splice(i, 1);
        },
        totalCount() {
            console.log("Count from method");
            return this.skills.length;
        }

    },
    computed: {
        totalCount1() {
            console.log("Count from computed property");
            return this.skills.length;
        },
        experiencedSkills() {
            let es = this.skills.filter((item) => {
                return item.experience >= 10;
            });
            return es;
        }

    }
}
</script>

<style>
li {
    list-style: none;
}
</style>