<template>
  <div class="app-container">
    <TheHeader />
    <NuxtPage />
    <TheFooter />
    <ChatButton />
  </div>
</template>

<script setup>
import TheHeader from '~/components/TheHeader.vue'
import TheFooter from '~/components/TheFooter.vue'
import ChatButton from '~/components/ChatButton.vue'
</script>

<style>
.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* 确保主内容区域占据剩余空间 */
main {
  flex: 1;
}

/* 全局样式 */
body {
  font-family: 'PingFang SC', 'Microsoft YaHei', sans-serif;
  color: #333;
  line-height: 1.6;
}

a {
  text-decoration: none;
  color: inherit;
}
</style> 