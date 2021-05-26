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
const img = "imgs/profiles/"+props.name+".png";
</script>

<template>
<div class="justify-center">
<div class="max-w-23">
    <div class="bg-dark-500 rounded-lg py-2 flex flex-col content-between -space-y-7">
    <span class="relative left-13 -top-3">
    <a :href="gh" target="_blank"
    class="icon-btn !border-none">
    <carbon-logo-github/>
    </a>
    </span>
        <div class="photo-wrapper">
        <img 
            class="w-12 h-12 rounded-full mx-auto border border-yellow-500" 
            :src="img" 
            :alt=props.name>
        </div>
        <div>
        <br>
            <p class="text-center text-gray-400">{{name}}</p>
            <p class="text-xs text-center">{{role}}</p>
        </div>
    </div>
</div>
</div>
</template>