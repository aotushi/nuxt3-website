<template>
  <header class="sticky top-0 z-50 w-full">
    <!-- 顶部蓝色条 -->
    <div class="bg-blue-600 text-white py-1 px-4 flex justify-end">
      <LanguageSwitcher />
    </div>
    
    <!-- 主导航栏 -->
    <div class="bg-gradient-to-r from-blue-50 to-blue-100 py-4">
      <div class="container mx-auto px-4 flex justify-between items-center">
        <!-- Logo -->
        <div class="flex items-center">
          <NuxtLink to="/" class="flex items-center">
            <span class="text-blue-600 text-3xl mr-2">
              <i class="fas fa-water"></i>
            </span>
            <span class="text-blue-900 text-xl font-bold">水滴互动</span>
          </NuxtLink>
        </div>
        
        <!-- 导航菜单 -->
        <nav class="hidden lg:flex items-center space-x-1">
          <div class="relative group">
            <button class="px-4 py-2 rounded-full flex items-center text-blue-900 hover:bg-blue-800 hover:text-white transition-colors">
              Why 水滴互动
              <i class="fas fa-chevron-down ml-2 text-xs"></i>
            </button>
            <DropdownMenu v-if="whyDropdownItems.length > 0" :items="whyDropdownItems" />
          </div>
          
          <div class="relative group">
            <button class="px-4 py-2 rounded-full flex items-center text-blue-900 hover:bg-blue-800 transition-colors">
              解决方案
              <i class="fas fa-chevron-down ml-2 text-xs"></i>
            </button>
            <DropdownMenu v-if="solutionDropdownItems.length > 0" :items="solutionDropdownItems" />
          </div>
          
          <div class="relative group">
            <button class="px-4 py-2 rounded-full flex items-center text-blue-900 hover:bg-blue-800 hover:text-white transition-colors">
              内容资源
              <i class="fas fa-chevron-down ml-2 text-xs"></i>
            </button>
            <DropdownMenu v-if="resourceDropdownItems.length > 0" :items="resourceDropdownItems" />
          </div>
          
          <div class="relative group">
            <button class="px-4 py-2 rounded-full flex items-center text-blue-900 hover:bg-blue-800 hover:text-white transition-colors">
              关于我们
              <i class="fas fa-chevron-down ml-2 text-xs"></i>
            </button>
            <DropdownMenu v-if="aboutDropdownItems.length > 0" :items="aboutDropdownItems" />
          </div>
        </nav>
        
        <!-- 免费网站诊断按钮 -->
        <div>
          <NuxtLink to="/diagnosis" class="bg-blue-600 text-white px-6 py-2 rounded-full hover:bg-blue-700 transition-colors">
            免费网站诊断
          </NuxtLink>
        </div>
        
        <!-- 移动端菜单按钮 -->
        <button class="lg:hidden text-blue-900" @click.prevent="toggleMobileMenu">
          <i class="fas fa-bars text-xl"></i>
        </button>
      </div>
    </div>
    
    <!-- 移动端菜单 -->
    <div v-if="mobileMenuOpen" class="lg:hidden bg-white shadow-lg absolute w-full">
      <div class="container mx-auto px-4 py-4">
        <div v-for="(section, index) in mobileMenuSections" :key="index" class="mb-4">
          <div class="font-bold text-blue-900 mb-2" @click.prevent="toggleSection(index)">
            {{ section.title }}
            <i :class="['fas', section.isOpen ? 'fa-chevron-up' : 'fa-chevron-down', 'ml-2']"></i>
          </div>
          <div v-if="section.isOpen" class="pl-4">
            <div v-for="item in section.items" :key="item.title" class="py-2">
              <NuxtLink :to="item.link" class="text-gray-700 hover:text-blue-600">
                {{ item.title }}
              </NuxtLink>
              <div v-if="item.description" class="text-sm text-gray-500">
                {{ item.description }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue';

const mobileMenuOpen = ref(false);
const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value;
};

const mobileMenuSections = ref([
  {
    title: 'Why 水滴互动',
    isOpen: false,
    items: [
      { title: '概述', link: '/why/overview', description: '是什么让ToB企业更愿意选择我们' },
      { title: '数据管理', link: '/why/data-management', description: '如何通过数据管理为增长赋能' },
      { title: '客户成功', link: '/why/customer-success', description: '哪些客户选择了我们' }
    ]
  },
  {
    title: '解决方案',
    isOpen: false,
    items: [
      { title: '中国搜索营销解决方案', link: '/solutions/china-search' },
      { title: '全球搜索营销解决方案', link: '/solutions/global-search' }
    ]
  },
  {
    title: '内容资源',
    isOpen: false,
    items: [
      { title: '内容资料', link: '/resources/content' },
      { title: '工具支持', link: '/resources/tools' }
    ]
  },
  {
    title: '关于我们',
    isOpen: false,
    items: [
      { title: '公司简介', link: '/about/company' }
    ]
  }
]);

const toggleSection = (index) => {
  mobileMenuSections.value[index].isOpen = !mobileMenuSections.value[index].isOpen;
};

// 下拉菜单数据
const whyDropdownItems = [
  { title: '概述', link: '/why/overview', description: '是什么让ToB企业更愿意选择我们' },
  { title: '数据管理', link: '/why/data-management', description: '如何通过数据管理为增长赋能' },
  { title: '客户成功', link: '/why/customer-success', description: '哪些客户选择了我们' }
];

const solutionDropdownItems = [
  { 
    title: '中国搜索营销解决方案', 
    link: '/solutions/china-search',
    subItems: [
      { title: '可追溯效果的SEO优化', link: '/solutions/china-search/seo', description: '数据驱动，可追溯可评估的SEO优化' },
      { title: '以增长付费的SEM投放', link: '/solutions/china-search/sem', description: '以终为始，落地企业降本增效的投放' },
      { title: '可量化ROI的内容营销', link: '/solutions/china-search/content', description: '结果导向，实现品效合一的内容增长' }
    ]
  },
  { 
    title: '全球搜索营销解决方案', 
    link: '/solutions/global-search',
    subItems: [
      { title: 'Google SEO', link: '/solutions/global-search/google-seo', description: '站内和站外优化服务，助力获取优质流量' },
      { title: '流媒体投放', link: '/solutions/global-search/media', description: '一站式代投服务，过程可控、效果客观' }
    ]
  }
];

const resourceDropdownItems = [
  { 
    title: '内容资料', 
    link: '/resources/content',
    subItems: [
      { title: '推广运营', link: '/resources/content/promotion' },
      { title: '网站优化', link: '/resources/content/website-optimization' },
      { title: '网络营销', link: '/resources/content/online-marketing' }
    ]
  },
  { 
    title: '工具支持', 
    link: '/resources/tools',
    subItems: [
      { title: '优化工具', link: '/resources/tools/optimization', description: '为您提供增长监控所需工具' },
      { title: 'D-MA顾问', link: '/resources/tools/dma', description: '加入D-MA顾问计划，成为资深顾问' }
    ]
  }
];

const aboutDropdownItems = [
  { title: '公司简介', link: '/about/company' }
];
</script> 