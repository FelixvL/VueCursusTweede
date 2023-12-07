<script setup>
const gedaan = "ja"
</script>
<template>
    <div>
        ToDoItem
        <br>
        <slot>Ja dit is fallback in the child</slot>
        <br>
        <slot name="deene"></slot>
        <br>
        <slot name="deandere"></slot>
        <br>
        <slot name="derde"></slot>
        <br>
        <slot name="vierde"></slot>
        <hr>
    </div>
</template>