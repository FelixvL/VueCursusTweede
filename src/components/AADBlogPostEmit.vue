<script setup>
const eigenschappen = defineProps(['titel'])
const demit = defineEmits(['derdeemit'])

function ffchecken(){
    console.log(eigenschappen.titel)
}
</script>
<template>
    <div>
        <button @click="$emit('enlarge-text')">Enlarge text</button>
        <button @click="$emit('ensmall-text')">Ensmall text</button>
        <h2>De titel: {{ titel }}</h2>
        <button @click="$emit('derdeemit')">derdeemit</button>
    </div>
</template>