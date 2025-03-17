<template>
  <div class="bg-white p-6 rounded-lg shadow-md">
    <div class="mb-4 text-blue-600">
      <i class="fas fa-quote-left text-2xl"></i>
    </div>
    <p class="italic text-gray-700 mb-6">{{ content }}</p>
    <div class="flex items-center">
      <img :src="avatar" :alt="name" class="w-12 h-12 rounded-full object-cover mr-4">
      <div>
        <h4 class="font-bold">{{ name }}</h4>
        <p class="text-sm text-gray-600">{{ position }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  content: {
    type: String,
    required: true
  },
  name: {
    type: String,
    required: true
  },
  position: {
    type: String,
    required: true
  },
  avatar: {
    type: String,
    default: 'https://source.unsplash.com/random/100x100/?portrait'
  }
});
</script> 