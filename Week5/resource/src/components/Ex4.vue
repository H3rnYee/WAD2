<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])

const newItem = ref('')

// TODO: Add Code Here
function removeItem(index){
   items.value.splice(index, 1)
}


function addItem(){
    if (!newItem.value) return
    items.value.push(newItem.value)
    newItem.value = ''
}

</script>

<template>

    <h2>Shopping Cart</h2>
      <ul>
         <li v-for="(item, index) in items" :key="item">
            {{ item }} <button v-on:click="removeItem(index)">Delete!</button>
         </li>
      </ul>
    <div>
        <form @submit.prevent="addItem">
            <input type="text" id="i" v-model="newItem"> 
            <button type="submit">Add!</button>
        </form>
    </div>

   
</template>
