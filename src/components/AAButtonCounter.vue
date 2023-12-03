<script setup>
import { ref } from 'vue'
const teller = ref(0)
function optellen(){
    this.teller++
}
</script>
<template>
    <div>
        Teller: {{ teller }} <button @click="optellen()">+</button>
    </div>
</template>