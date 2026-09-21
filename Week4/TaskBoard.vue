<script setup>
import { computed, ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()

function goBack() {
  router.push('/')
}


const tasks = ref([
  { id: 1, title: 'Review Vue reactivity', category: 'Web Development', priority: 'high', estimate: 40, status: false, color: 'white' },
  { id: 2, title: 'Complete routing exercise', category: 'Assignments', priority: 'medium', estimate: 30, status: true, color: '#000000' },
  { id: 3, title: 'Read component patterns', category: 'Reading', priority: 'low', estimate: 20, status: false, color: '#f0b35a' }
])



// DIY: implement addTask function
function addTask() {
 
}


</script>

<template>
  <h1>Tasks</h1>
  
  <section class="done"
      style="border: '2px solid orange'">
    
    <h2>Review Vue reactivity</h2>
    <p>Priority: High </p>
    <p>Duration: 40 mins</p>
    <p>Status:
      <span class="status-chip">Done 😀</span>
    </p>

    <button>Done</button>
    <button>Not yet</button>

  </section>

  <section>
    <h1>Add A New Task</h1>

    title: <input type="text" placeholder="title">
    Priority: <select>
      <option>high</option>
      <option>medium</option>
      <option>low</option>
    </select>
    Category: <select>
      <option>Web Development</option>
      <option>Assignments</option>
      <option>Reading</option>
    </select>
    Estimate: <input type="number">
    Color: <input type="color">
    <button>Add New Task</button>
  </section>

  <br>
  <button class="back-link" @click="goBack">← Back to Home</button>

</template>

<style scoped>
.high {
  color: rgba(0, 26, 255, 0.503);
}

.medium {
  color: aquamarine;
}

.low {
  color: rgb(165, 149, 42);
}

.done {
  background-color: green;
}
.notyet {
  background-color: red;
}

.spacing {
  padding: 10px;
}


</style>
