<template>
    <div>
      <p>Chiều rộng cửa sổ: {{ windowWidth }} px</p>
    </div>
  </template>
  
  <script lang="ts">
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  
  const GetWidthWindow = {
    setup() {
      const windowWidth = ref(window.innerWidth); 
  
      const updateWindowWidth = () => {
        windowWidth.value = window.innerWidth; 
      };
  
      
      onMounted(() => {
        window.addEventListener('resize', updateWindowWidth);
      });
  
      onBeforeUnmount(() => {
        window.removeEventListener('resize', updateWindowWidth);
      });
  
      return {
        windowWidth,
      };
    },
  };
  
  export { GetWidthWindow };
  </script>
  
  <style scoped>
  </style>
  