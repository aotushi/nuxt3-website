<template>
  <div class="absolute left-0 mt-2 w-80 bg-white rounded-lg shadow-lg overflow-hidden z-50 opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300">
    <div class="p-4">
      <div v-for="item in items" :key="item.title" class="mb-4">
        <NuxtLink :to="item.link" class="font-semibold text-blue-900 hover:text-blue-600">
          {{ item.title }}
        </NuxtLink>
        <div v-if="item.description" class="text-sm text-gray-600 mt-1">
          {{ item.description }}
        </div>
        <div v-if="item.subItems && item.subItems.length > 0" class="mt-2 pl-2 border-l-2 border-blue-100">
          <div v-for="subItem in item.subItems" :key="subItem.title" class="mb-2">
            <NuxtLink :to="subItem.link" class="text-blue-800 hover:text-blue-600">
              {{ subItem.title }}
            </NuxtLink>
            <div v-if="subItem.description" class="text-xs text-gray-500">
              {{ subItem.description }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  items: {
    type: Array,
    default: () => []
  }
});
</script> 