
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

    <h4>ref name: {{ name }}</h4>
    <h4>reactive name: {{ person.name }}</h4>
    <h4>reavtive age: {{ person.age }}</h4>

    <h4 class="mt-3">V-for</h4>
    <ul>
      <li v-for="pink in pinks" :key="pink">
        {{pink}}
      </li>
    </ul>

    <h4>V-for with Object</h4>
    <ul>
      <li v-for="pinkObj in pinksObj">
        <div>{{ pinkObj.name }}</div>
        <div>{{ pinkObj.age }}</div>
      </li>
    </ul>

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
        {name: 'Lisa', age: 24},
        {name: 'Rose', age: 21},
        {name: 'Jinne', age: 25},
        {name: 'Jiso', age: 20}

      ])
      
</script>


<style scoped>

</style>
