<script setup>
import axios from 'axios';
import { ref } from 'vue';
const moods = ref(['Happy', 'Sad', 'Angry']);
const subject = ref('');
const entry = ref('');
const mood = ref('');

// Add Code Here
const submitPost = async () =>{
    const url = 'http://localhost:8000/posts'
    try {
        await axios.post(url, {
            subject: subject.value,
            entry: entry.value,
            mood: mood.value,
        })

    } catch (error) {
    console.log('unable to save',error.message)
    }
}

</script>

<template>
    <div class="table m-2">
        <h3>Add a New Blog Post</h3>

        Subject: <input type='text' size='30' v-model='subject' required>
        <br>

        Entry: <br>
        <textarea name='entry' cols='80' rows='5' v-model='entry' required></textarea>
        <br>

        Mood:
        <!-- TODO: Build a dropdown list here for selecting the mood -->
        <select v-model="mood">
            <option value="happy">happy</option>
            <option value="sad">sad</option>
            <option value="angry">angry</option>
            <option value="bored">bored</option>

        </select>
        <br>

        <br>
        <button v-on:click="submitPost">Submit New Post</button>

        <hr>
        <RouterLink to="/ViewPosts/">Click  here to return to Main Page</RouterLink>  
       
    </div>
</template>

