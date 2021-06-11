<script setup lang="ts">
import { defineProps, ref } from 'vue'

const props = defineProps({
  name: {
    type: String,
  },
  role: {
    type: String
  },
  github: {
    type: String
  }
})
const gh = "https://github.com/"+props.github
const img = "kedro-retro-june-2021/"+props.name.toString().replace('\s+', '_').toLowerCase()+".png";
</script>

<template>
<div class="justify-center">
<div class="w-23 shadow-lg">
    <div class="bg-dark-500 rounded-lg flex flex-col">
    <span class="relative left-14 -top-2">
    <a :href="gh" target="_blank"
    class="icon-btn !border-none">
    <carbon-logo-github/>
    </a>
    </span>
        <div class="photo-wrapper -mt-7">
        <img 
            class="w-12 h-12 rounded-full mx-auto border border-yellow-500" 
            :src="img" 
            :alt=props.name
            hover="animate-spin"
        >
        </div>
        <div class="">
            <p class="text-1.0em text-center text-gray-300">{{name}}</p>
            <p class="text-0.7em text-center">{{role}}</p>
        </div>
    </div>
</div>
</div>
</template>