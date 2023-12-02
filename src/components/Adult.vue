<template>
    <!-- Computed -->
        <!-- <p>First Name: {{ firstName1 }}</p>
        <p>Last Name: {{ lastName1 }}</p>
        <p>FullName: {{ fullName1 }}</p>
        <p>Number 1: {{ num1 }}</p>
        <p>Number 2: {{ num2 }}</p>
        <p>Total Name: {{ totalNum }}</p> -->

        <!-- Adult person -->
        <div class="card my-5 text-bg-light" style="max-width: 55rem; margin: auto;">
        <div class="card-body">
            <div class="mb-3">
            <input type="text" @keyup.enter="addPerson" v-model="person.name" class="form-control" placeholder="Name">
            </div>
            <div class="mb-3">
            <input type="text" @keyup.enter="addPerson" v-model.number="person.age" class="form-control" placeholder="Age">
            </div>
            <button @click="addPerson" class="btn btn-sm btn-primary">+ Add</button>
            <hr>
            <div class="row">
                <div class="col-md-4">
                    <h4>People</h4>
                    <ul>
                        <li v-for="person in people" :key="person.name">Name: {{person.name}} / Age: {{ person.age }}</li>
                    </ul>
                </div>
                <div class="col-md-4">
                    <h4>Adults People</h4>
                    <ul>
                        <li v-for="adult in adults">Name: {{ adult.name}} / Age: {{ adult.age }}</li>
                    </ul>
                </div>
                <div class="col-md-4">
                    <h4>Youngs People</h4>
                    <ul>
                        <li v-for="young in youngs">Name: {{ young.name}} / Age: {{ young.age }}</li>
                    </ul>
                </div>       
            </div>
        </div>
        </div>
</template>

<script setup>
    import {computed, ref, reactive} from 'vue';
    //Computed 
    const firstName1 = ref('Nan')
      const lastName1 = ref('Dar')
      const fullName1 = computed(() => {
        return `${firstName1.value}  ${lastName1.value}`;
      })
      const num1 = ref(100)
      const num2 = ref(200)
      const totalNum = computed(() => {
        return num1.value + num2.value
      })

      //Adult
      //show
      const people = ref([
        {
          name: 'Tun',
          age: 17
        },
        {
          name: 'Hla',
          age: 21
        },
        {
          name: 'Dar',
          age: 25
        },
        {
          name: 'Min',
          age: 20
        }
      ])

      //write
      const person = reactive({
        name:'',
        age: ''
      })
      const addPerson = () => {
        people.value.push({...person})
        person.name = '',
        person.age = ''
      }

      const adults = computed(() => {
        return people.value.filter((person) => {
            return person.age >= 21
        })
      })
      const youngs = computed(() => {
        return people.value.filter((person) => {
            return person.age < 21
        })
      })

</script>

<style scoped>

</style>