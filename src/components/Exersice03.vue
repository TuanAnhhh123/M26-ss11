<template>
    <div>
      <p>Age: {{ age }}</p>
      <p>Company: {{ selectedCompany }}</p>
      <button @click="randomizeAge">Random</button>
    </div>
  </template>
  
  <script lang="ts">
  import { ref, onMounted, onUpdated } from 'vue';
  
  export default {
    setup() {
      const age = ref(1);
      const companies = ["Rikkei Academy", "Rikkei Education", "Rikkei Fukuoka"];
      const selectedCompany = ref(companies[0]);
  
      const randomizeAge = () => {
        age.value = Math.floor(Math.random() * 10) + 1;
      };
  
      const updateSelectedCompany = () => {
        selectedCompany.value = companies[(age.value - 1) % companies.length];
      };
  
      onMounted(() => {
        updateSelectedCompany();
      });
  
      onUpdated(() => {
        updateSelectedCompany();
      });
  
      return {
        age,
        companies,
        selectedCompany,
        randomizeAge,
      };
    },
  };
  </script>
  
  <style scoped>
  </style>
  