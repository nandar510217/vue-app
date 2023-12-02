<template>
    <div class="container">
        <div class=" card border-secondary mt-5">
            <h3 class="text-center card-header py-3">Form Handling</h3>
            <div class="card-body text-secondary">
                <div class="row">
                    <div class="col-md-4">
                        <h3>User Info</h3>
                        <label for="">Name</label>
                        <input type="text" v-model="userInfo.name" class="form-control">
                        <label for="">Email</label>
                        <input type="text" v-model="userInfo.email" class="form-control">
                        <label for="">Address</label>
                        <textarea name="" v-model="userInfo.address" rows="3" class="form-control"></textarea>
                        <div>
                        <label for="">City</label>
                        <select v-model="userInfo.city" class="form-control">
                            <option value="Monywa">Monywa</option>
                            <option value="Taungyi">Taungyi</option>
                            <option value="Mandalay">Mandalay</option>
                            <option value="Yangon">Yangon</option>
                        </select>
                        </div>
                        <div>
                        <label for="">Roles</label>
                        <select v-model="userInfo.roles" class="form-control" multiple>
                            <option value="Student">Student</option>
                            <option value="Programer">Programer</option>
                            <option value="Freelance">Freelance</option>
                        </select>
                        </div>
                        <div class="mt-3">
                        <label for="">Single</label><br>
                        <input type="checkbox" v-model="userInfo.isSingle" true-value="yes" false-value="no">
                        </div>
                        <div class="mt-3">
                        <label for="">Hobbies</label><br>
                        <input type="checkbox" v-model="userInfo.hobbies" value="Coding">Coding<br>
                        <input type="checkbox" v-model="userInfo.hobbies" value="Reading">Reading<br>
                        <input type="checkbox" v-model="userInfo.hobbies" value="Playing">Playing<br>
                        </div>
                        <div class="mt-3">
                            <label for="">Gender</label>
                            <div>
                                <input type="radio" v-model="userInfo.gender" value="Male" class="me-1" id="male">
                                <label for="male" class="me-2">Male</label>
                                <input type="radio" v-model="userInfo.gender" value="Female " class="me-1" id="female">
                                <label for="female">Female</label>  
                            </div>
                            </div>
                        <div class="mt-3">
                        <button class="btn btn-sm btn-primary" @click="submit">Submit</button>
                        </div>
                    </div>
                    <div class="col-md-8">
                        <table class="table table-bordered table-hover mt-5">
                            <thead>
                                <tr>
                                <td>No</td>
                                <td>Name</td>
                                <td>Email</td>
                                <td>Address</td>
                                <td>City</td>
                                <td>Role</td>
                                <td>Marital Status</td>
                                <td>Hobbies</td>
                                <td>Gender</td>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="user in users">
                                <td>1</td>
                                <td>{{ user.name }}</td>
                                <td>{{ user.email }}</td>
                                <td>{{ user.address}}</td>
                                <td>{{ user.city }}</td>
                                <td>
                                    <div v-for="role in roles">{{ user.roles }}</div>
                                </td>
                                <td>{{ user.isSingle }}</td>
                                <td>
                                    <div v-for="hobby in hobbies">{{ user.hobbies }}</div>
                                </td>
                                <td>{{ user.gender }}</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
// import { ref } from 'vue';

//     const name = ref('sfioe')
//     const test = ref('test')

//     const email = ref('dd')
//     const testemail = ref('')

//     const submit = () =>{
//         test.value = name.value;
//         testemail.value = email.value
//     }

import { ref, reactive } from 'vue';

//show data
const users = ref([
    {
        name: 'nan dar',
        email: 'nan@gmail.com',
        address: '',
        city: 'Monywa',
        roles: [],
        isSingle: "yes",
        hobbies: [], 
        gender: 'Male',     
    }
])

//write input
const userInfo = reactive({
    name: '',
    email: '',
    address: '',
    city: '',
    roles: [],
    isSingle: "yes",
    hobbies: [], 
    gender: 'Male',
})

const submit = () => {
    // const user = {...userInfo}
    // users.value.push({user}) (or)

    users.value.push({...userInfo})
    
    userInfo.name = '';
    userInfo.email= '';
    userInfo.address= '';
    userInfo.city= '';
    userInfo.roles= [];
    userInfo.isSingle= "yes";
    userInfo.hobbies= [];
    userInfo.gender= 'Male';
}

</script>

<style scoped>

</style>
