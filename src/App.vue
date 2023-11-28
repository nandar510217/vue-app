
<template>
  <nav class="navbar navbar-expand-lg bg-info">
  <div class="container">
    <a class="navbar-brand" href="#">Vue.js</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Features</a>
        </li>
      </ul>
    </div>
  </div>
  </nav>
  <div class="container py-3">
    <h1>Hello</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. In eligendi dignissimos quis accusamus cumque, doloremque sequi, minima ipsam optio possimus error veritatis similique eos, alias nihil qui ea tempora fuga!</p>

    <div class="row">
      <!-- V show -->
      <h3 v-show="isTrue">V show</h3>
      <div class="d-flex">
        <div class="card card-body mx-2" v-if="isTrue">
          1. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Porro, reiciendis.
        </div>
        <div class="card card-body mx-2" v-else-if="is2ndTrue">
          2. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Porro, reiciendis.
        </div>
        <div class="card card-body mx-2" v-else>
          3. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Porro, reiciendis.
        </div> 
        <div v-if="5>4">
          <div class="card card-body mx-2">
            4. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Porro, reiciendis.
          </div>  
        </div>     
      </div>
    </div>
    <div class="row my-3">
      <div class="d-flex">
        <template v-if="isTrue">
          <div class="card mx-3">1. Lorem ipsum dolor sit amet.</div>
          <div class="card mx-3">2. Lorem ipsum dolor sit amet.</div>
        </template>
        <div class="card mx-3">3. Lorem ipsum dolor sit amet.</div>
      </div>
    </div>

    <div class="row my-4" v-if="isTrueshow">
      <div class="col-md-6">
        <h4>ref name: {{ name }}</h4>
        <h4>reactive name: {{ person.name }}</h4>
        <h4>reavtive age: {{ person.age }}</h4>

        <h4 class="mt-3">V-for</h4>
        <ul>

          <!-- <li v-for="(val,key) in [1,2,3,4]">{{ val }} index- {{ key }}</li> -->
          
          <li v-for="(pink,index) in pinks" :key="index">
            {{index}} - {{pink}}
          </li>
        </ul>

        <h4>V-for with Object</h4>
        <ul>
          <li v-for="pinkObj in pinksObj" :key="pinkObj.name">
            <div>{{ pinkObj.name }}</div>
            <div>{{ pinkObj.age }}</div>
            <ul v-for="lang in pinkObj.language">
              <li>{{ lang }}</li>
            </ul>
          </li>
        </ul>

        <h4>Object loop</h4>
        <ul>
          <li v-for="p in person1">{{p}}</li>
        </ul>

        <h4>V-for with V-if Directive</h4>
        <ul>
          <template v-for="bp in blackPinks" :key="bp.name">
            <li v-if="bp.age > 21">
              <div>{{ bp.name }}</div>
              <div>{{ bp.age }}</div>
            </li>
        </template>
        </ul>
      </div>

      <div class="col-md-6">
        <h4>Acessing data in Method</h4>
        <p>Full Name: {{ fullName() }}</p>

        <h4>Event Handling - Inline Handler</h4>
        <h5>{{ count }}</h5>
        <button class="btn btn-primary me-2" @click="count++">Increase</button>
        <button class="btn btn-primary" @click="count--">Decrease</button>

        <h4>Event Handling - Method Handler</h4>
        <h5>{{ number }}</h5>
        <button class="btn btn-warning me-2" @click="add()">Add 1</button>
        <button class="btn btn-danger me-2" @click="reduce()">Reduce 1</button><br><br>
        <button class="btn btn-success me-2" @click="showAlert()">Show Alert</button>
        <button class="btn btn-success me-2" @click="nativeEvent($event, 'Nan Dar')">Native Event</button>
      </div>
    </div>
    
    <div class="row">
      <div class="col-md-6">
        <h3>User Info</h3>
        <label for="">Name</label>
        <input type="text" v-model="userInfo.name1" class="form-control">
        <label for="">Email</label>
        <input type="text" v-model="userInfo.email1" class="form-control">
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
          <label for="">Gender</label><br>
          <input type="radio" v-model="userInfo.gender" value="Male">Male<br>
          <input type="radio" v-model="userInfo.gender" value="Female ">Female<br>
        </div>
        <div class="mt-3">
          <button class="btn btn-sm btn-primary" @click="storeUserInfo">Submit</button>
        </div>
      </div>
      <div class="col-md-6">
        <div>{{ userInfo.name1 }}</div>
        <div>{{ userInfo.email1 }}</div>
        <div>{{ userInfo.address }}</div>
        <div>{{ userInfo.city }}</div>
        <div>{{ userInfo.roles }}</div>
        <div>{{ userInfo.isSingle }}</div>
        <div>{{ userInfo.hobbies }}</div>
        <div>{{ userInfo.gender }}</div>
      </div>
    </div>

  </div> 
</template>

<script setup>
  import {ref, reactive} from 'vue';
  
      const isTrue = ref(true)
      const is2ndTrue = ref(true)

      //
      const name = ref('Lisa')
      const person = reactive({
        name: 'Kelvin',
        age: 25
      })

      name.value = "mg mg"
      person.age = 20

      console.log(name.value)
      console.log(person.age)

      //V-for Directive
      const pinks = ref(['Lisa', 'Rose', 'Jinne', 'Jiso'])
      const pinksObj = ref([
        {name: 'Lisa', age: 24, language: ['English', 'Thai', 'Korean']},
        {name: 'Rose', age: 21, language: ['Thai', 'Korean']},
        {name: 'Jinne', age: 25, language: ['English', 'Thai', 'Japanese']},
        {name: 'Jiso', age: 20, language: ['English', 'Korean']}
      ])

      //Object loop
      const person1 = reactive({name: 'John', age: 20})

      //v-for with v-if directive
      const blackPinks = ref([
        { name: 'LISA', age: 23},
        { name: 'ROSE', age: 25},
        { name: 'JISO', age: 20},
        { name: 'JENIE', age: 21}
      ]) 

      //Accessing data in Method
      const firstName = ref('Nan')
      const lastName = ref('Dar')
      const fullName = () => {
        // return firstName+ ' ' + lastName;  (or)
        return `${firstName.value} ${lastName.value}`
      }

      //Event Handling - Inline Handler
      const count = ref(0)
      //Event Handling - Method Handler
      const number = ref(0)
      const add = () => {
        number.value++;
      }
      const reduce = () => {
        number.value--;
      }
      const showAlert = () => {
        alert('Alert function in js')
      }
      const nativeEvent = (e, name) => {
        console.log(e)
        console.log('Hello' + name)
      }

      const isTrueshow = ref(false)

      //Form Handling
      const userInfo = reactive({
        name1: '',
        email1: '',
        address: '',
        city: '',
        roles: [],
        isSingle: "yes",
        hobbies: [], 
        gender: 'Male'
      })

      const storeUserInfo = () => {
        console.log(userInfo);
      }
      
</script>


<style scoped>

</style>
