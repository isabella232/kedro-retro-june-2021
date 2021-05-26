<script setup lang="ts">
import { computed, defineProps } from 'vue'
const props = defineProps({
  class: {
    type: String,
  },
  url: {
   type: String
  }
})

</script>

<template>
  <div class="grid grid-cols-2 w-full h-full">
    <div class="slidev-layout default" :class="props.class">
      <slot />
    </div>
    <div>
      <iframe 
        id="frame"
        class="w-full h-full"  
        :src="props.url"
        >
      </iframe>
    </div>
  </div>


</template>
