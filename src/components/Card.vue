<template>
    <div class="col-md-3">
        <div class="card card-body my-2">
            <p>{{ cardTitle }}</p>
            <Button :btnName="btnName" someClasses="btn-success" />
        </div>
    </div>

</template>

<script setup>
    import Button from './Button.vue';
    defineProps(['cardTitle', 'btnName' ])

</script>

<style scoped>

</style>