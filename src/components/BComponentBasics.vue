<script setup>
    import { ref } from 'vue'
    import { onMounted } from 'vue'
    import { onBeforeMount } from 'vue'
    import { onActivated } from 'vue'
    import { onBeforeUpdate } from 'vue'
    
    const getal = ref(5)

    onMounted(() => {
        console.log(`the component is now mounted.`)
    })
    onBeforeMount(() => {
        console.log(`the component before Mount.`)
    })
    onActivated(() => {
        console.log(`the component is Activated.`)
    })
    onBeforeUpdate(() => {
        console.log(`the component before Updated.`)
    })

    function a(){
        getal.value += 1
    }
</script>
<template>
    <div>
        Component B {{ getal }}
        <button @click="a()">+</button>
    </div>
</template>