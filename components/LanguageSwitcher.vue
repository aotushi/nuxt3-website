<template>
  <div class="flex space-x-4">
    <button 
      @click.prevent="setLanguage('zh')" 
      :class="['hover:underline', currentLanguage === 'zh' ? 'font-bold' : '']"
    >
      中文
    </button>
    <button 
      @click.prevent="setLanguage('en')" 
      :class="['hover:underline', currentLanguage === 'en' ? 'font-bold' : '']"
    >
      English
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const currentLanguage = ref('zh');

const setLanguage = (lang) => {
  currentLanguage.value = lang;
  // 这里可以添加实际的语言切换逻辑
};
</script> 