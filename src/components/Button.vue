<template>
    <div>
        <button class="btn btn-sm" :class="someClasses">{{btnName}}</button>
    </div>
</template>

<script setup>
    defineProps(['btnName', 'someClasses'])
 
</script>

<style scoped>

</style>