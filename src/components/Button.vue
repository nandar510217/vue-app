<template>
    <div>
        <button class="btn btn-sm" :class="someClasses">{{btnName}}</button>
    </div>
</template>

<script setup>
    // defineProps(['btnName', 'someClasses'])
    defineProps({
        btnName: {
            type: [String,Number],
            required:true,
            default: 'default'
        },
        someClasses: String
    })
 
</script>

<style scoped>

</style>