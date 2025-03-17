<template>
  <div class="bg-blue-50 p-6 rounded-lg hover:shadow-md transition-shadow">
    <h3 class="text-xl font-bold text-blue-900 mb-4">{{ title }}</h3>
    <p class="text-gray-700 mb-6">{{ description }}</p>
    <NuxtLink :to="link" class="inline-block bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">
      了解更多
    </NuxtLink>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  link: {
    type: String,
    default: '#'
  }
});
</script> 