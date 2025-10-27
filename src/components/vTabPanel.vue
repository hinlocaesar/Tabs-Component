<script setup>
const props = defineProps({
  title: String
})

import { inject } from 'vue'

const message = inject('tab-key')

</script>
<template>
  <div class="tab-content" v-if="title === message">
    <slot></slot>
  </div>

  
  
</template>
