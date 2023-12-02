<template>
    <div class="my-2 card text-bg-info p-4">
        <h3 class="text-center mb-3">To Do Lists</h3>
        <div class="input-group mb-3">
            <input type="text" @keyup.enter="addTodo" class="form-control" v-model="inputTodo">
            <button class="btn btn-secondary" @click="addTodo" type="submit" id="button-addon2">Add</button>
        </div>
        <ul class="list-group">
            <li v-for="showTodolist in showTodolists" :key="showTodolist" class="list-group-item">
                <input class="form-check-input me-1" type="checkbox" value="" id="firstCheckbox">
                <label class="form-check-label" for="firstCheckbox">{{ showTodolist}}</label>
            </li>
        </ul>
    </div>
</template>

<script setup>
    import { ref, reactive } from 'vue';
    //show note
    const showTodolists = ref([
        'Wake up',
        'Take a bath',
        'Have a lunch',
        'Learning vue',
    ])
    //write note
    const inputTodo = ref('')

    const addTodo = () => {
        showTodolists.value.push(inputTodo.value)
        inputTodo.value = '';
    }

</script>

<style scoped>

</style>