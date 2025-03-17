<template>
  <div class="bg-white rounded-full p-1 shadow-md hover:shadow-lg transition-shadow">
    <div class="bg-blue-900 rounded-full p-6 text-center">
      <div class="bg-white rounded-full w-16 h-16 mx-auto flex items-center justify-center mb-4">
        <i :class="['text-blue-600 text-2xl', icon]"></i>
      </div>
      <h3 class="text-white font-bold mb-2">{{ title }}</h3>
      <button class="bg-white text-blue-900 px-4 py-1 rounded-full text-sm font-medium hover:bg-blue-50 transition-colors">
        了解更多
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    required: true
  }
});
</script> 