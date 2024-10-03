<template>
<div>
    <div v-if="isshow">
        <!-- <ChildrenComponent/> -->
         <!-- <Time/> -->
    </div>
  <h1>Parent Component</h1>
  <button @click="hadleShow">Toggle</button>

</div>
</template>

<script setup>
// import ChildrenComponent from './ChildrenComponent.vue';
// import Time from './Time.vue';
import { ref } from 'vue';
const isshow = ref(false);
const hadleShow = () =>{
    isshow.value = !isshow.value;
}
</script>

<style>

</style>