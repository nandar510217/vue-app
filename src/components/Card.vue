<template>
    <div v-for="item in items" :key="item.id" class="col-md-3">
        <div class="card card-body my-2">
            <h4 class="my-3">{{ item.name }}</h4>
            <Button someClasses="btn-success" />
        </div>
    </div>

</template>

<script setup>
    import Button from './Button.vue';
    import { inject } from 'vue';
    // defineProps(['cardTitle'])
    const items = inject('items')

</script>

<style scoped>

</style>