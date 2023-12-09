<template>
    <div>
        <button class="btn btn-sm" :class="someClasses">{{btnName}}</button>
    </div>
</template>

<script setup>
import { inject } from 'vue';

    defineProps(['someClasses'])
    // defineProps({
    //     btnValue: {
    //         type: [String,Number],
    //         required:true,
    //         default: 'default'
    //     },
    //     someClasses: String
    // })

    //provide and inject
    const btnName = inject('btnValue')
 
</script>

<style scoped>

</style>