<template>
  <div>
    <!-- 英雄区域 -->
    <section class="bg-gradient-to-r from-blue-50 to-blue-100 pt-8 pb-16">
      <div class="container mx-auto px-4">
        <div class="grid md:grid-cols-2 gap-8 items-center">
          <div>
            <div class="mb-8">
              <h1 class="text-4xl md:text-5xl font-bold text-blue-900 mb-6">B2B行业数字营销增长</h1>
              <p class="text-lg text-gray-700 mb-8">
                为企业提供数据驱动的数字营销解决方案，助力企业实现业务增长。 我们的专业团队将为您定制最适合的营销策略。
              </p>
              <button class="bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 transition-colors">
                免费咨询服务 <i class="fas fa-arrow-right ml-2"></i>
              </button>
            </div>
          </div>
          <div class="relative">
            <img src="../assets/imgs/home-banner.png" alt="B2B数字营销" class="rounded-lg shadow-lg w-full" />
            <div class="absolute top-4 right-4 bg-white rounded-lg shadow-lg p-4">
              <div class="text-center">
                <div class="text-3xl font-bold text-blue-600">83.5</div>
                <div class="text-sm text-gray-600">/100</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 统计数据 -->
    <section class="py-12 bg-white">
      <div class="container mx-auto px-4">
        <h2 class="text-2xl md:text-3xl font-bold text-center text-blue-900 mb-4">83.7% 了解过水滴互动的企业，选择了我们！</h2>
        <p class="text-center text-gray-700 mb-12 max-w-3xl mx-auto">
          每一个与我们合作的客户都获得了显著的业务增长和营销效果提升。我们的数据驱动方法确保每一分投入都能产生最大回报。
        </p>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="text-center">
            <div class="bg-blue-900 rounded-full w-24 h-24 mx-auto flex items-center justify-center mb-4">
              <img src="../assets/imgs/home-list-1.png" />
            </div>
            <h3 class="font-bold text-xl mb-2">行业及人群洞察</h3>
            <button class="bg-blue-600 text-white px-4 py-1 rounded-full text-sm">了解更多</button>
          </div>

          <div class="text-center">
            <div class="bg-blue-900 rounded-full w-24 h-24 mx-auto flex items-center justify-center mb-4">
              <img src="../assets/imgs/home-list-2.png" />
            </div>
            <h3 class="font-bold text-xl mb-2">数据模型搭建</h3>
            <button class="bg-blue-600 text-white px-4 py-1 rounded-full text-sm">了解更多</button>
          </div>

          <div class="text-center">
            <div class="bg-blue-900 rounded-full w-24 h-24 mx-auto flex items-center justify-center mb-4">
              <img src="../assets/imgs/home-list-3.png" />
            </div>
            <h3 class="font-bold text-xl mb-2">客户增长加速</h3>
            <button class="bg-blue-600 text-white px-4 py-1 rounded-full text-sm">了解更多</button>
          </div>
        </div>
      </div>
    </section>

    <!-- 解决方案 -->
    <section class="py-12 bg-blue-50">
      <div class="container mx-auto px-4">
        <h2 class="text-2xl md:text-3xl font-bold text-center text-blue-900 mb-4">为独一无二的品牌提供增长解决方案</h2>
        <p class="text-center text-gray-700 mb-12 max-w-3xl mx-auto">
          水滴互动 针对营销增长策略的每一环节提供综合解决方案，
          通过海外搜索营销、国内搜索营销、品牌一体化建设三个解决方案包助您打造全球营销路径。
        </p>

        <!-- PC端布局 - 左侧文字列表，右侧图片 -->
        <div class="hidden lg:flex gap-8 relative">
          <!-- 左侧竖线 -->
          <div class="absolute left-0 top-0 bottom-0 w-1 bg-gray-200"></div>
          
          <!-- 左侧文字列表 -->
          <div class="w-1/2 pr-8">
            <div 
              v-for="(item, index) in solutionItems" 
              :key="index"
              class="relative pl-8 pb-16 cursor-pointer solution-item"
              :class="{ 'active': activeIndex === index }"
              @mouseenter="activeIndex = index"
            >
              <!-- 激活状态的竖线 -->
              <div 
                class="absolute left-0 top-0 bottom-0 w-1 bg-blue-600 transition-all duration-300"
                :class="{ 'opacity-100': activeIndex === index, 'opacity-0': activeIndex !== index }"
              ></div>
              
              <h3 class="text-2xl font-bold text-blue-900 mb-4">{{ item.title }}</h3>
              <p class="text-gray-700 mb-4">{{ item.description }}</p>
              <a :href="item.link" class="inline-block bg-blue-600 text-white px-4 py-2 rounded-full text-sm hover:bg-blue-700 transition-colors">
                {{ item.buttonText }}
              </a>
            </div>
          </div>
          
          <!-- 右侧图片 -->
          <div class="w-1/2 relative">
            <div 
              v-for="(item, index) in solutionItems" 
              :key="`img-${index}`"
              class="absolute inset-0 transition-opacity duration-500 rounded-full overflow-hidden"
              :class="{ 'opacity-100': activeIndex === index, 'opacity-0': activeIndex !== index }"
            >
              <div class="relative w-full h-full flex justify-center items-center">
                <img :src="item.image" :alt="item.title" class="w-400 h-400 object-cover rounded-full" />
                <!-- <div class="absolute left-4 top-1/2 transform -translate-y-1/2 bg-blue-900 rounded-full w-12 h-12 flex items-center justify-center">
                  <i :class="item.icon" class="text-white text-xl"></i>
                </div> -->
              </div>
            </div>
          </div>
        </div>
        
        <!-- 平板和移动端布局 -->
        <div class="lg:hidden space-y-12">
          <div 
            v-for="(item, index) in solutionItems" 
            :key="`mobile-${index}`"
            class="flex flex-col"
          >
            <h3 class="text-xl md:text-2xl font-bold text-blue-900 mb-4 text-center">{{ item.title }}</h3>
            
            <!-- 图片区域 -->
            <div class="relative w-full mb-6">
              <div class="aspect-w-16 aspect-h-9 md:aspect-w-4 md:aspect-h-3 rounded-full overflow-hidden mx-auto" style="max-width: 500px;">
                <img :src="item.image" :alt="item.title" class="w-full h-full object-cover" />
                <div class="absolute left-4 top-1/2 transform -translate-y-1/2 bg-blue-900 rounded-full w-12 h-12 flex items-center justify-center">
                  <i :class="item.icon" class="text-white text-xl"></i>
                </div>
              </div>
            </div>
            
            <!-- 文字描述 -->
            <p class="text-gray-700 mb-4 text-center md:px-12">{{ item.description }}</p>
            
            <!-- 按钮居中 -->
            <div class="text-center">
              <a :href="item.link" class="inline-block bg-blue-600 text-white px-6 py-2 rounded-full text-sm hover:bg-blue-700 transition-colors">
                {{ item.buttonText }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 客户反馈 -->
    <section class="py-16 bg-blue-50">
      <div class="container mx-auto px-4">
        <h2 class="text-2xl md:text-3xl font-bold text-center text-blue-900 mb-12">与客户共同成功</h2>
        
        <div class="flex flex-col md:flex-row gap-6">
          <!-- 客户反馈卡片1 -->
          <div class="bg-white rounded-lg shadow-md p-8 flex-1">
            <!-- <div class="text-blue-500 text-4xl mb-4">
              <i class="fas fa-quote-left"></i>
            </div> -->
            <p class="text-gray-700 mb-6">
              Their organization skills are not to be underestimated.They truly go above and beyond to make sure their clients are successful and is a great addition to any demand gen team.
            </p>
            <div class="mt-auto">
              <h4 class="font-bold text-gray-900">Han M.</h4>
              <p class="text-gray-600 mb-4">Senior Manager, Digital Marketing<br />— Personio</p>
              
              <div class="inline-block bg-gray-100 rounded-full px-4 py-2 text-sm">
                Google 自然搜索转换量提升比: <span class="font-bold">87.3%</span>
              </div>
            </div>
          </div>
          
          <!-- 客户反馈卡片2 -->
          <div class="bg-white rounded-lg shadow-md p-8 flex-1">
            <!-- <div class="text-blue-500 text-4xl mb-4">
              <i class="fas fa-quote-left"></i>
            </div> -->
            <p class="text-gray-700 mb-6">
              作为一家CRM厂商，我们的客户需求场景庞杂，中小型客户占比较多，如何低成本获得客户成为我们最大的问题。
              借助水滴互动的搜索营销策略，通过SEO和SEM来进行网络营销，帮助我们低成本的获得大量MQL，实现了业务增长。
            </p>
            <div class="mt-auto">
              <h4 class="font-bold text-gray-900">王先生</h4>
              <p class="text-gray-600 mb-4">市场VP — XToolCRM</p>
              
              <div class="inline-block bg-gray-100 rounded-full px-4 py-2 text-sm">
                通过百度自然搜索降低线索成本: <span class="font-bold">43.7%</span>
              </div>
            </div>
          </div>
          
          <!-- 客户反馈卡片3 -->
          <div class="bg-white rounded-lg shadow-md p-8 flex-1">
            <!-- <div class="text-blue-500 text-4xl mb-4">
              <i class="fas fa-quote-left"></i>
            </div> -->
            <p class="text-gray-700 mb-6">
              中国市场是一个非常有价值的市场。在中国，DTS一直在进行数字营销。
              我们对搜索优化和品牌媒体建设进行了组合使用，建设了一套有成效的数字营销流程，大大提升了营销管理效率，且更符合中国法规。
            </p>
            <div class="mt-auto">
              <h4 class="font-bold text-gray-900">五十嵐さん</h4>
              <p class="text-gray-600 mb-4">部长<br />— 株式会社DTS</p>
              
              <div class="inline-block bg-gray-100 rounded-full px-4 py-2 text-sm">
                2022年度实现年度目标完成率: <span class="font-bold">143.5%</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import solution1 from '~/assets/imgs/home-solution-1.png'
import solution2 from '~/assets/imgs/home-solution-2.png'
import solution3 from '../assets/imgs/home-solution-3.png'
export default {
  data() {
    return {
      activeIndex: 0,
      solutionItems: [
        {
          title: '海外搜索营销解决方案',
          description: 'Google——全球用户数量最多的搜索引擎，平均每秒需要处理超过40,000次查询，也就是说每天会有35亿的搜索行为正在发生，您的潜在客户当然也在这其中。',
          buttonText: 'google-SEO解决方案',
          link: '/solutions/google-seo',
          image: solution1,
          icon: 'fas fa-globe'
        },
        {
          title: '国内搜索营销解决方案',
          description: '通过整站SEO优化，提升官网搜索 引擎友好度，增加网站收录、权重、排名、用户体验及转化效果，从而获取优质搜索流量，增加官网商业价值。',
          buttonText: '中文SEO解决方案',
          link: '/solutions/chinese-seo',
          image: solution2,
          icon: 'fas fa-file-alt'
        },
        {
          title: '品牌全球一体化解决方案',
          description: '专注于为ToB行业软件类产品出海提供一站式营销推广解决方案，帮助出海企业和出海品牌实现品效协同和业务飞跃。',
          buttonText: '品牌出海解决方案',
          link: '/solutions/global-brand',
          image: solution3,
          icon: 'fas fa-bolt'
        }
      ]
    }
  }
}
</script>

<style scoped>
.solution-item:hover h3 {
  color: #2563eb; /* blue-600 */
}

/* 确保图片容器在移动端有正确的宽高比 */
@media (max-width: 768px) {
  .aspect-w-16.aspect-h-9 {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 比例 */
  }
  
  .aspect-w-16.aspect-h-9 img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
</style>
