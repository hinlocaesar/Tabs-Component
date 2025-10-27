<script setup>
import {ref} from 'vue';
import { provide } from 'vue'


const activeTab = ref('Vue')
provide('tab-key', activeTab)

const handleActiveTab = (val) =>{
  activeTab.value = val;

}

</script>

<template>
  <div class="tabs">
    <div class="tab-trigger-wrapper">
      <button 
        v-for="item in ['Vue.js','React','Svelte']"
        :key="item"
        class="tab-trigger"
        :class="{ active: activeTab == item }"
        @click="handleActiveTab(item)"
      >
        {{item}}
      </button>
      
    </div>
    <div class="tab-content-wrapper">
      <slot></slot>
    </div>
  </div>
</template>
