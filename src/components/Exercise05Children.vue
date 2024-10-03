<template>
    <div>
      <p>Child component is visible.</p>
    </div>
  </template>
  
  <script lang="ts">
  import { ref, onBeforeUnmount, onUnmounted } from 'vue';
  
  export default {
    setup() {
      onBeforeUnmount(() => {
        console.log("beforeUnmount: Component is about to be unmounted");
      });
  
      onUnmounted(() => {
        console.log("unmounted: Component has been unmounted");
      });
  
      return {};
    },
  };
  </script>
  
  <style scoped>
  </style>
  