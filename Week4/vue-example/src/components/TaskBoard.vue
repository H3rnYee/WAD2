<script setup>
//To write JS code
//ref library is used to make the data 'reactive'
import {ref} from 'vue'

const title = ref('Vue is Awesome!')
const imgSrc = ref('../assets/logo.svg')
const tasks = ref([
    {id: 1, title: 'Review Vue reactivity', category: 'Web Development', priority: 'high', estimate: 40, status: false, color: 'white'},
    {id: 2, title: 'Complete routing exercise', category: 'Assignments', priority: 'medium', estimate: 30, status: true, color: '#000000'},
    {id: 3, title: 'Read component patterns', category: 'Reading', priority: 'low', estimate: 20, status: false, color: '#f0b35a'}
])

function updateStatus(){
    alert('BUTTTONS')
    //update task.status to done, i need to CHANGE THIS
    task.status = true
}
//if you have a data that is not needed to be reactivd, just define like a normal variable
const notReactive = 'Static Data'
</script>

<template>
<!--To write HTML-->
<!-- attribute binding-->
<img v-bind:src='imgSrc'>

<!-- basic data binding: interpolation {{ }}-->
<h1>{{ title }}</h1>

<div v-for = "(task, idx) in tasks" :key='idx'
    v-bind:class = "{'done': task.status, 'notyet':!task.status}"
    
    :style = "{'color': task.color, 'border': '2px solid orange'}"
    >
    {{idx}}

    <h2>{{task.title}}</h2>
    <p>Priority: {{task.priority}}</p>

    <!--on click, update-->
    <button v-on:click="updateStatus()">Done</button>

</div>

</template>

<style scoped>
/*To write CSS*/
.done{
    background-color:green;
    margin: 5px
}
.notyet{
    background-color:red;
    margin:5px;
}
</style>
