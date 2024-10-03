<template>
    <div class="traffic-light">
      <div
        class="light"
        :class="{ active: currentLight === 'green' }"
        @click="toggleLight('green')"
      >
        <span v-if="currentLight === 'green'">{{ countdown }}s</span>
      </div>
      <div
        class="light"
        :class="{ active: currentLight === 'yellow' }"
        @click="toggleLight('yellow')"
      >
        <span v-if="currentLight === 'yellow'">{{ countdown }}s</span>
      </div>
      <div
        class="light"
        :class="{ active: currentLight === 'red' }"
        @click="toggleLight('red')"
      >
        <span v-if="currentLight === 'red'">{{ countdown }}s</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentLight: 'red', 
        intervalId: null,
        countdown: 0,
        changeLightInterval: null,
      };
    },
    mounted() {
      this.startTrafficLight();
    },
    beforeUnmount() {
      clearInterval(this.intervalId); 
      clearInterval(this.changeLightInterval); 
    },
    methods: {
      startTrafficLight() {
        this.setCountdown(40); 
        this.intervalId = setInterval(() => {
          this.changeLight();
        }, 5000);
      },
      changeLight() {
        if (this.currentLight === 'red') {
          this.currentLight = 'green';
          this.setCountdown(60); 
        } else if (this.currentLight === 'green') {
          this.currentLight = 'yellow';
          this.setCountdown(3); 
        } else if (this.currentLight === 'yellow') {
          this.currentLight = 'red';
          this.setCountdown(40); 
        }
      },
      setCountdown(seconds = 0) {
        this.countdown = seconds;
        clearInterval(this.changeLightInterval); 
  
        this.changeLightInterval = setInterval(() => {
          this.countdown--;
          if (this.countdown <= 0) {
            clearInterval(this.changeLightInterval);
          }
        }, 10000); 
      },
      toggleLight(light) {
        this.currentLight = light;
        if (light === 'green') {
          this.setCountdown(60); 
        } else if (light === 'yellow') {
          this.setCountdown(3); 
        } else if (light === 'red') {
          this.setCountdown(40); 
        }
      },
    },
  };
  </script>
  
  <style>
  .traffic-light {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .light {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin: 5px;
    background-color: grey;
    transition: background-color 0.3s;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
  }
  
  .light.active {
    background-color: currentColor;
  }
  
  .light.active:nth-child(1) {
    color: green;
  }
  
  .light.active:nth-child(2) {
    color: yellow;
  }
  
  .light.active:nth-child(3) {
    color: red;
  }
  </style>
  