<template>
    <div>
        <h3 class="text-center mb-3 mt-5">To Do List</h3>
        <div class="input-group mb-3">
          <input type="text" class="form-control" v-model="inputTodo">
          <button class="btn btn-secondary" @click="addTodo" type="submit" id="button-addon2">Add</button>
        </div>
        <!-- <ul>
            <li>eriowi</li>
        </ul> -->
        <ul class="list-group">
            <li v-for="showTodolist in showTodolists" class="list-group-item">
                <input class="form-check-input me-1" type="checkbox" value="" id="firstCheckbox">
                <label class="form-check-label" for="firstCheckbox">{{ showTodolist}}</label>
            </li>
        </ul>
    </div>
</template>

<script setup>
    import { ref, reactive } from 'vue';
    //show note
    const showTodolists = reactive([
        'wake up',
        'take a bath',
    ])
    //write note
    const inputTodo = ref('')

    const addTodo = () => {
        showTodolists.push(inputTodo.value)
        inputTodo.value = '';
    }

</script>

<style scoped>

</style>