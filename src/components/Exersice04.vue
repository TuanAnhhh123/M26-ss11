<template>
    <div>
      <p>Child Age: {{ age }}</p>
    </div>
  </template>
  
  <script>
  import { ref, onMounted, onUpdated } from 'vue';
  
  const ChildComponent = {
    props: {
      age: {
        type: Number,
        required: true,
      },
    },
  
    setup(props) {
      const previousAge = ref(props.age);
  
      onMounted(() => {
        console.log('Component mounted with initial age:', props.age);
      });
  
      onUpdated(() => {
       
        if (props.age !== previousAge.value) {
          console.log(`Age has changed from ${previousAge.value} to ${props.age}`);
          previousAge.value = props.age;
        }
      });
  
      return {};
    },
  };
  
  export { ChildComponent }; 
  </script>
  
  <style scoped>
  </style>
  