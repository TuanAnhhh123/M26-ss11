<!-- <template>
    <div>
  <h1>Children Component</h1>
  <input type="text" v-model="inputValue">
  <h2>Count : {{ count }}</h2>
  <button @click="hadleCount">Count</button>
  </div>
</template>

<script setup>
import { onBeforeMount , onBeforeUnmount, onBeforeUpdate, onMounted ,onUpdated,ref } from 'vue';
const count = ref(0);
const inputValue = ref("");
const hadleCount = () =>{
    count.value++;
}
onBeforeMount(()=>{
    // count.value =5;
    console.log("Components before mount");
    
});
onMounted(()=>{
    // count.value =6;
    console.log("Component Mounted");
    
});
onBeforeUpdate(()=>{
    document.title = inputValue.value;
    console.log("BeforeUpdate");
    
});
onUpdated(()=>{
    inputValue.value = "Nguyễn Văn A"
    console.log("Component Update");
      
});
onBeforeUnmount(()=>{
    console.log("Component Unmount");
    
})
</script>

<style>

</style> -->