<template>
  <div class="text-center">
    <div class="text-4xl font-bold text-blue-600 mb-2">{{ value }}</div>
    <div class="text-gray-700">{{ label }}</div>
  </div>
</template>

<script setup>
defineProps({
  value: {
    type: String,
    required: true
  },
  label: {
    type: String,
    required: true
  }
});
</script> 