<template>
    <div class="card-body">
        <p>{{ info }}</p>
        <button class="btn btn-info float-end" @click="$emit('closeInfo', 'data from child')">Close</button>
        
    </div>
</template>

<script setup>
    defineProps(['info'])

</script>

<style scoped>

</style>