<template>
    <div>
      <h1>Thời gian hiện tại: {{ time }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        time: this.getCurrentTime(),
      };
    },
    methods: {
      getCurrentTime() {
        const now = new Date();
        const hours = String(now.getHours()).padStart(2, '0');
        const minutes = String(now.getMinutes()).padStart(2, '0');
        const seconds = String(now.getSeconds()).padStart(2, '0');
        return `${hours} : ${minutes} : ${seconds}`;
      },
      updateClock() {
        this.time = this.getCurrentTime();
      },
    },
    mounted() {
      this.interval = setInterval(this.updateClock, 1000);
    },
    beforeUnmount() {
      clearInterval(this.interval);
    },
  };
  </script>
  
  <style scoped>
  h1 {
    font-family: Arial, sans-serif;
    font-size: 2rem;
    text-align: center;
  }
  </style>