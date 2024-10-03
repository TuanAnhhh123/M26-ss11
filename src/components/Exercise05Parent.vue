<template>
    <div>
      <button @click="toggleChild">Toggle</button>
      <Exercise05Children v-if="isChildVisible" />
    </div>
  </template>
  
  <script lang="ts">
  import { ref } from 'vue';
  import Exercise05Children from './Exercise05Children.vue';
  
  const Exercise05Parent = {
    components: {
      Exercise05Children,
    },
  
    setup() {
      const isChildVisible = ref(false);
  
      const toggleChild = () => {
        isChildVisible.value = !isChildVisible.value;
      };
  
      return {
        isChildVisible,
        toggleChild,
      };
    },
  };
  
  export { Exercise05Parent }; 
  </script>
  
  <style scoped>
  </style>
  