<script setup>
const eigenschappen = defineProps(['titel'])
function ffchecken(){
    console.log(eigenschappen.titel)
}
</script>
<template>
    <div>
        <h2>De titel: {{ titel }}</h2>
        <button @click="ffchecken()">c</button>
    </div>
</template>