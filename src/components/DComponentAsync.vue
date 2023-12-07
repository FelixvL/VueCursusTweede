<script setup>
import { ref } from 'vue'
import { defineAsyncComponent } from 'vue'
import CCBSlotsProps from './CCBSlotsProps.vue'
import AAButtonCounter from './AAButtonCounter.vue';
const AdminPage = defineAsyncComponent(() =>
  import('./DDAAsyncDing.vue')
)
const AsyncComp = defineAsyncComponent({
  // the loader function
  loader: () => import('./DDAAsyncDing.vue'),

  // A component to use while the async component is loading
  loadingComponent: CCBSlotsProps,
  // Delay before showing the loading component. Default: 200ms.
  delay: 200,

  // A component to use if the load fails
  errorComponent: AAButtonCounter,
  // The error component will be displayed if a timeout is
  // provided and exceeded. Default: Infinity.
  timeout: 3000
})
</script>
<template>
  a  
  <AdminPage />
  <AsyncComp />
</template>
