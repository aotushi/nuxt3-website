<template>
  <div class="fixed bottom-6 right-6 z-50">
    <button 
      @click.prevent="toggleChat" 
      class="bg-blue-600 hover:bg-blue-700 text-white w-14 h-14 rounded-full flex items-center justify-center shadow-lg transition-all"
    >
      <i :class="['fas', isOpen ? 'fa-times' : 'fa-comments', 'text-xl']"></i>
    </button>
    
    <div 
      v-if="isOpen" 
      class="absolute bottom-16 right-0 w-80 bg-white rounded-lg shadow-xl overflow-hidden transition-all duration-300"
    >
      <div class="bg-blue-600 text-white p-4">
        <h3 class="font-bold">在线客服</h3>
        <p class="text-sm">我们将尽快回复您的问题</p>
      </div>
      <div class="p-4 h-80 overflow-y-auto bg-gray-50">
        <div class="space-y-4">
          <div class="flex justify-start">
            <div class="bg-white p-3 rounded-lg shadow-sm max-w-xs">
              <p class="text-sm">您好！欢迎访问水滴互动，请问有什么可以帮助您的？</p>
              <span class="text-xs text-gray-500 block mt-1">客服小水滴 10:30</span>
            </div>
          </div>
        </div>
      </div>
      <div class="p-4 border-t">
        <div class="flex">
          <input 
            type="text" 
            placeholder="请输入您的问题..." 
            class="flex-1 border border-gray-300 rounded-l-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-600"
          >
          <button class="bg-blue-600 text-white px-4 py-2 rounded-r-lg hover:bg-blue-700">
            <i class="fas fa-paper-plane"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isOpen = ref(false);

const toggleChat = () => {
  isOpen.value = !isOpen.value;
};
</script> 