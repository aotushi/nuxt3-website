<template>
  <footer class="bg-blue-900 text-white py-12">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
        <div>
          <h3 class="text-lg font-bold mb-4">公司信息</h3>
          <ul class="space-y-2">
            <li><a href="#" class="hover:text-blue-300">关于我们</a></li>
            <li><a href="#" class="hover:text-blue-300">联系方式</a></li>
            <li><a href="#" class="hover:text-blue-300">加入我们</a></li>
          </ul>
        </div>
        
        <div>
          <h3 class="text-lg font-bold mb-4">解决方案</h3>
          <ul class="space-y-2">
            <li><a href="#" class="hover:text-blue-300">中国搜索营销</a></li>
            <li><a href="#" class="hover:text-blue-300">全球搜索营销</a></li>
            <li><a href="#" class="hover:text-blue-300">内容营销</a></li>
            <li><a href="#" class="hover:text-blue-300">SEO优化</a></li>
            <li><a href="#" class="hover:text-blue-300">SEM投放</a></li>
          </ul>
        </div>
        
        <div>
          <h3 class="text-lg font-bold mb-4">资源中心</h3>
          <ul class="space-y-2">
            <li><a href="#" class="hover:text-blue-300">博客文章</a></li>
            <li><a href="#" class="hover:text-blue-300">案例研究</a></li>
            <li><a href="#" class="hover:text-blue-300">白皮书</a></li>
            <li><a href="#" class="hover:text-blue-300">行业报告</a></li>
          </ul>
        </div>
        
        <div>
          <h3 class="text-lg font-bold mb-4">联系我们</h3>
          <ul class="space-y-2">
            <li class="flex items-center">
              <i class="fas fa-map-marker-alt mr-2"></i>
              <span>上海市浦东新区XX路XX号</span>
            </li>
            <li class="flex items-center">
              <i class="fas fa-phone mr-2"></i>
              <span>400-123-4567</span>
            </li>
            <li class="flex items-center">
              <i class="fas fa-envelope mr-2"></i>
              <span>contact@waterdrops.com</span>
            </li>
          </ul>
          <div class="mt-4">
            <div class="flex space-x-4 mt-2">
              <a href="#" class="text-white hover:text-blue-300">
                <i class="fab fa-weixin text-xl"></i>
              </a>
              <a href="#" class="text-white hover:text-blue-300">
                <i class="fab fa-weibo text-xl"></i>
              </a>
              <a href="#" class="text-white hover:text-blue-300">
                <i class="fab fa-linkedin text-xl"></i>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="border-t border-blue-800 mt-8 pt-6 text-center text-sm">
        <p>&copy; {{ new Date().getFullYear() }} 水滴互动. 保留所有权利.</p>
      </div>
    </div>
  </footer>
</template> 