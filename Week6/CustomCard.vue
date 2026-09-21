<script setup>
import { ref } from 'vue'
// input 
const props = defineProps( ['entry', 'imgSrc'] )

const likes = ref(0)

const unlikes = ref(0)

function doLike() {
    likes.value++ 
}

function doUnlike() {
    unlikes.value++
}

</script>

<template>

    <div class="card w-50">
        <img v-bind:src="'/' + imgSrc.toLowerCase() + '.png'" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title"> card 1 </h5>
            <p class="card-text">{{ entry }}</p>
            <a href="#" class="btn btn-primary" v-on:click="doLike">#Likes {{ likes }}</a>
            <a href="#" class="btn btn-danger" @click="doUnlike">#DisLikes {{ unlikes }}</a>
        </div>
    </div>

</template>