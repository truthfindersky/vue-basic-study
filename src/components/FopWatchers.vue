<template>
    <div>
        <h1>Option API: Watchers</h1>

        <div>
            <h4>Vloume Trucker (0-20)</h4>
            <h4>Current Volume {{volume}}</h4>
            <button @click="volume += 2">Increase</button>
            <button @click="volume -= 2">Decrease</button>
        </div>

        <div>
            <h4>Another example</h4>
            <input
                type="text"
                v-model="mobile"
                placeholder="Enter 11 digit mobile number" 
            />
        </div>
        
        <div>
            <h4>Imatmedie Watchers</h4>
            <input type="text" v-model="movie">
        </div>

       
        <div>
            <h4>Deep Watchers</h4>
            <input type="text" v-model="movieInfo.title"><br><br>
            <input type="text" v-model="movieInfo.actor"><br><br>
            <button @click="movieList.push('Wonder Woman')">Add Movie</button>
        </div>
    </div>
</template>

<script>

export default {
    name: 'FopWatchers',
    data() {
        return {
            volume: 0,

            mobile: '',

            movie: 'Batman',

            movieInfo: {
                title: '',
                actor: ''
            },
            movieList: ['Batman', 'Superman']
        }
    },
    methods: {},
    computed: {},
    watch: {
        volume(newVolume, oldValue) {
            if (newVolume > oldValue && newVolume === 16) {
                alert('High Volume')
            }
        },

        mobile(newValue, oldValue) {
            console.log(newValue);

            if (isNaN(newValue)) {
                alert("Enter valid mobile number");
                this.mobile = oldValue;
            }

            if (newValue.length == 11) {
                alert("An OTP has been sent");
            }
        },

        movie: {
            handler(newValue) {
                console.log(`Calling API with movie name = ${newValue}`)
            },
            immediate: true //inform browser handler function should run initially when page load
        },

        movieInfo: {
            handler(newValue) {
                console.log(`Calling API with movue title = ${newValue.title} and actor = ${newValue.actor}`)
            },
            deep: true //watcher doesn't execute for object if not use deep: true
        },
        movieList: {
            handler(newValue) {
                console.log(`Updated list ${newValue}`)
            },
            deep: true //watcher doesn't execute for array if not use deep: true
        }
    }
}
</script>