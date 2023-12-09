<template>
    <div class="card-body">
        <h4>Component Style with blue color</h4>
        <p>{{ info }}</p>
        <button class="btn btn-info float-end" @click="$emit('closeInfo', 'data from child')">Close</button>
        <input type="text" v-model="inputText">
    </div>
</template>

<script setup>
import { onMounted, onBeforeMount, onBeforeUnmount, onUnmounted, onUpdated, ref, onBeforeUpdate } from 'vue';

    defineProps(['info'])

    const inputText = ref('Just Text');

    onMounted(function(){
        console.log('onMounted is register');
    })

    onBeforeMount(() => {
        console.log('onBeforeMounted is register');
    })

    onUnmounted(() => {
        console.log('onUnmounted is register');
    })

    onBeforeUnmount(() => {
        console.log('onBeforeUnmount is register');
    })

    onUpdated(()=> {
        console.log('onUpdated is register')
    })

    onBeforeUpdate(() => {
        console.log('onBeforeUpdate is register')
    })

</script>

<style scoped>
h4{
    color: blue;
}

</style>