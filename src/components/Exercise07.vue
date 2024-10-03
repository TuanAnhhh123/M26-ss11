<template>
    <div>
      <input v-model="inputValue" placeholder="Nhập tên để cập nhật tiêu đề" />
    </div>
  </template>
  
  <script lang="ts">
  import { ref, onMounted } from 'vue';
  
  const Exercise07 = {
    setup() {
      const inputValue = ref(''); 
  
      onMounted(() => {
        document.title = 'Nhập tên để cập nhật tiêu đề';
      });
  
     
      const updateTitle = () => {
        document.title = inputValue.value || 'Nhập tên để cập nhật tiêu đề'; 
      };
  
      return {
        inputValue,
        updateTitle,
      };
    },
    watch: {
      inputValue: {
        handler: function(newValue) {
          this.updateTitle(); 
        },
        immediate: true, 
      },
    },
  };
  
  export { Exercise07 };
  </script>
  
  <style scoped>
  </style>
  