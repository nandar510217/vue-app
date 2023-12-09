<template>
    <div>
        <h4>Watcher</h4>
        <input type="text" v-model="input1"><br>
        <input type="text" v-model="input2" class="my-3">
    </div>
</template>

<script setup>
import { onUpdated, ref, watch } from 'vue';

    
    const input1 = ref('just test 1')
    const input2 = ref('just test 2')

    watch(input1, () => {
        console.log(input1.value)
    })

    onUpdated(()=> {
        console.log('onUpdated is working')
    })
</script>

<style lang="scss" scoped>

</style>