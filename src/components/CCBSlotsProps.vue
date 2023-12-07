<script setup>
const gedaan = "ja"
const inderdaad = "misschien"
const minder = "anders nooit iets"
</script>
<template>
    <div>
        <slot :autonaam="inderdaad" :ikhebnogmeer="minder"></slot>
        <slot name="weereennaam" :zomaar="inderdaad"></slot>
    </div>
</template>