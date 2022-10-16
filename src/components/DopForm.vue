<template>
    <div class="container">
        <h1>Vue Form</h1>
        <div>
            <pre>
               {{JSON.stringify(formValues, null, 2)}}
            </pre>
        </div>
        <!-- .prevent  -->
        <form @submit.prevent="submitForm">
            <div class="form-group p-2">
                <label for="name">Name</label>
                <input type="text" class="form-control" id="name" v-model.trim.lazy="formValues.name">
                <!-- .trim avoids space, .lazy to update after mouse click -->
            </div>
            <div class="form-group p-2">
                <label for="profile">Profile Summery</label>
                <textarea type="text" class="form-control" id="profile" v-model="formValues.profileSummery"></textarea>
            </div>
            <div class="form-group col-md-4 p-2">
                <label for="country">Country</label>
                <select id="country" class="form-control" v-model="formValues.country">
                    <option selected>Choose...</option>
                    <option value="Bangladesh">Bangladeh</option>
                    <option value="India">India</option>
                    <option value="Vietnam">Vietnam</option>
                </select>
            </div>
            <div class="form-group col-md-4 p-2">
                <label for="job-location">Job Location</label>
                <select id="job-location" class="form-control" v-model="formValues.jobLocation" multiple>
                    <option value="bangladesh">Bangladeh</option>
                    <option value="india">India</option>
                    <option value="vietnam">Vietnam</option>
                </select>
            </div>
            <div class="form-check p-2">
                <input type="checkbox" class="form-check-input" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
                <label class="form-check-label" for="remoteWork">Open to remote work</label>
            </div>
            <div>
                <label>Skill</label>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" value="html" id="html" v-model="formValues.skillSet" />
                    <label class="form-check-label" for="html">Html</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" value="css" id="css" v-model="formValues.skillSet" />
                    <label class="form-check-label" for="css">Css</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" value="php" id="php" v-model="formValues.skillSet" />
                    <label class="form-check-label" for="php">PHP</label>
                </div>
            </div>
            <div>
                <label>years Of Experience</label>
                <div class="form-check">
                    <input class="form-check-input" type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience" checked>
                    <label class="form-check-label" for="0-2">0-2</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience">
                    <label class="form-check-label" for="3-5">3-5</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="radio" id="6-10" value="6-10" v-model="formValues.yearsOfExperience">
                    <label class="form-check-label" for="6-10">6-10</label>
                </div>
            </div>
            <div>
                <div class="form-group p-2">
                    <label for="age">Age</label>
                    <input type="number" class="form-control" id="age" v-model.number="formValues.age">
                </div>
            </div>
            <div>
                <button type="submit" class="btn btn-primary p-2">Submit</button>
            </div>
        </form>
    </div>
</template>



<script>

export default {
    name: 'DopForm',
    data() {
        return {
            formValues: {
                name: '',
                profileSummery: '',
                country: '',
                jobLocation: [],
                remoteWork: 'no',
                skillSet: [],
                yearsOfExperience: '0-2',
                age: null
            }

        }
    },
    methods: {
        submitForm() {
            //event.preventDefault();
            console.log('Form Values', this.formValues);
        }
    }
}
</script>