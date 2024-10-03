<template>
    <div>
      <button @click="increment">Increment</button>
      <p>Count: {{ count }}</p>
    </div>
  </template>
  
  <script lang="ts">
  import { ref } from 'vue';
  
  const Exercise06 = {
    setup() {
      const count = ref(0); 
  
      const increment = () => {
        count.value++; 
        document.title = `Count: ${count.value}`; 
      };
  
      return {
        count,
        increment,
      };
    },
  };
  
  export { Exercise06 }; 
  </script>
  
  <style scoped>
  </style>
  