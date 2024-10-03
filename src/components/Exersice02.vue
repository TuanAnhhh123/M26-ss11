<template>
    <div>
      <p>Count: {{ count }}</p>
      <button @click="increment">Counter</button>
    </div>
  </template>
  
  <script lang="ts">
  import { ref, onMounted, onUpdated } from 'vue';
  
  export default {
    setup() {
      const count = ref(0);
  
      const increment = () => {
        count.value++;
      };
  
      onMounted(() => {
        console.log("Component mounted");
      });
  
      onUpdated(() => {
        console.log("Dữ liệu đã thay đổi");
      });
  
      return {
        count,
        increment,
      };
    },
  };
  </script>
  
  <style scoped>
  </style>
  