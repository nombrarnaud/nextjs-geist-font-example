<template>
  <div class="digital-marketing">
    <!-- Hero Section -->
    <section class="relative py-24 bg-gradient-to-br from-primary-600 via-orange-500 to-primary-700 text-white overflow-hidden">
      <div class="absolute inset-0 bg-black/10"></div>
      <div class="container-max relative z-10">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="animate-slide-up">
            <h1 class="text-5xl font-bold font-heading mb-6">
              {{ $t('services.digitalMarketing.title') }}
            </h1>
            <p class="text-xl text-white/90 mb-8">
              {{ $t('services.digitalMarketing.subtitle') }}
            </p>
            <p class="text-lg text-white/80 mb-8">
              {{ $t('services.digitalMarketing.description') }}
            </p>
            <router-link to="/contact" class="btn-secondary">
              Boost Your Marketing
            </router-link>
          </div>
          
          <!-- Illustration -->
          <div class="relative animate-fade-in" style="animation-delay: 0.5s;">
            <div class="relative w-full h-96">
              <!-- Marketing Dashboard -->
              <div class="absolute inset-0 bg-white/20 backdrop-blur-sm rounded-2xl p-6">
                <div class="bg-white rounded-lg p-4 h-full">
                  <div class="flex items-center justify-between mb-4">
                    <h3 class="text-gray-900 font-semibold">Marketing Analytics</h3>
                    <div class="flex space-x-2">
                      <div class="w-3 h-3 bg-green-400 rounded-full animate-pulse"></div>
                      <span class="text-xs text-gray-600">Live</span>
                    </div>
                  </div>
                  
                  <!-- Chart Area -->
                  <div class="h-32 mb-4 relative">
                    <div class="absolute bottom-0 left-0 w-full flex items-end space-x-2">
                      <div class="bg-primary-300 rounded-t" style="height: 60%; width: 12%"></div>
                      <div class="bg-orange-300 rounded-t" style="height: 80%; width: 12%"></div>
                      <div class="bg-primary-300 rounded-t" style="height: 45%; width: 12%"></div>
                      <div class="bg-orange-300 rounded-t" style="height: 90%; width: 12%"></div>
                      <div class="bg-primary-300 rounded-t" style="height: 70%; width: 12%"></div>
                      <div class="bg-orange-300 rounded-t" style="height: 55%; width: 12%"></div>
                    </div>
                  </div>
                  
                  <!-- Metrics -->
                  <div class="grid grid-cols-3 gap-2 text-xs">
                    <div class="text-center">
                      <div class="text-primary-600 font-bold">+125%</div>
                      <div class="text-gray-500">Traffic</div>
                    </div>
                    <div class="text-center">
                      <div class="text-orange-600 font-bold">+89%</div>
                      <div class="text-gray-500">Leads</div>
                    </div>
                    <div class="text-center">
                      <div class="text-green-600 font-bold">+67%</div>
                      <div class="text-gray-500">Sales</div>
                    </div>
                  </div>
                </div>
              </div>
              
              <!-- Floating Marketing Icons -->
              <div class="absolute -top-4 -right-4 w-16 h-16 bg-white rounded-xl shadow-xl flex items-center justify-center animate-float">
                <span class="text-2xl">📈</span>
              </div>
              <div class="absolute -bottom-4 -left-4 w-14 h-14 bg-white rounded-xl shadow-xl flex items-center justify-center animate-float" style="animation-delay: 2s;">
                <span class="text-xl">🎯</span>
              </div>
              <div class="absolute top-1/2 -right-8 w-12 h-12 bg-white rounded-full shadow-xl flex items-center justify-center animate-float" style="animation-delay: 4s;">
                <span class="text-lg">💡</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="section-padding bg-white">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Our Marketing Services
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Comprehensive digital marketing strategies to grow your online presence
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(service, index) in services" :key="index" 
               class="card p-8 animate-slide-up" 
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="w-16 h-16 bg-gradient-to-r from-primary-500 to-orange-600 rounded-xl flex items-center justify-center mb-6">
              <span class="text-white text-2xl" v-html="service.icon"></span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 mb-4">{{ service.title }}</h3>
            <p class="text-gray-600 mb-4">{{ service.description }}</p>
            <ul class="space-y-2">
              <li v-for="feature in service.features" :key="feature" class="flex items-center text-sm text-gray-600">
                <span class="w-2 h-2 bg-orange-500 rounded-full mr-3"></span>
                {{ feature }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Strategy Section -->
    <section class="section-padding bg-gray-50">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Our Marketing Strategy
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Data-driven approach to maximize your marketing ROI
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(step, index) in strategy" :key="index" 
               class="text-center animate-slide-up" 
               :style="{ animationDelay: `${index * 0.2}s` }">
            <div class="w-20 h-20 bg-gradient-to-r from-primary-500 to-orange-600 rounded-full flex items-center justify-center mx-auto mb-6">
              <span class="text-white text-2xl font-bold">{{ index + 1 }}</span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 mb-4">{{ step.title }}</h3>
            <p class="text-gray-600">{{ step.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Results Section -->
    <section class="section-padding bg-white">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Proven Results
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Real metrics from our successful marketing campaigns
          </p>
        </div>

        <div class="grid grid-cols-2 lg:grid-cols-4 gap-8">
          <div class="text-center animate-slide-up">
            <div class="text-4xl font-bold text-gradient mb-2">+250%</div>
            <div class="text-gray-600">Average Traffic Increase</div>
          </div>
          <div class="text-center animate-slide-up" style="animation-delay: 0.1s;">
            <div class="text-4xl font-bold text-gradient mb-2">+180%</div>
            <div class="text-gray-600">Lead Generation Growth</div>
          </div>
          <div class="text-center animate-slide-up" style="animation-delay: 0.2s;">
            <div class="text-4xl font-bold text-gradient mb-2">+95%</div>
            <div class="text-gray-600">Conversion Rate Improvement</div>
          </div>
          <div class="text-center animate-slide-up" style="animation-delay: 0.3s;">
            <div class="text-4xl font-bold text-gradient mb-2">4.8x</div>
            <div class="text-gray-600">Average ROI</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Case Studies -->
    <section class="section-padding bg-gray-50">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Success Stories
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Real case studies from our marketing campaigns
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(study, index) in caseStudies" :key="index" 
               class="card p-8 animate-slide-up" 
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="flex items-center mb-6">
              <div class="w-12 h-12 bg-gradient-to-r from-primary-500 to-orange-600 rounded-lg flex items-center justify-center mr-4">
                <span class="text-white text-xl" v-html="study.icon"></span>
              </div>
              <div>
                <h3 class="text-lg font-semibold text-gray-900">{{ study.company }}</h3>
                <p class="text-gray-600 text-sm">{{ study.industry }}</p>
              </div>
            </div>
            <p class="text-gray-600 mb-6">{{ study.description }}</p>
            <div class="grid grid-cols-2 gap-4">
              <div class="text-center">
                <div class="text-2xl font-bold text-gradient">{{ study.metric1.value }}</div>
                <div class="text-xs text-gray-500">{{ study.metric1.label }}</div>
              </div>
              <div class="text-center">
                <div class="text-2xl font-bold text-gradient">{{ study.metric2.value }}</div>
                <div class="text-xs text-gray-500">{{ study.metric2.label }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Tools & Platforms -->
    <section class="section-padding bg-white">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Marketing Tools & Platforms
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            We use the best tools to deliver exceptional marketing results
          </p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-8">
          <div v-for="(tool, index) in tools" :key="index" 
               class="text-center animate-slide-up" 
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="w-16 h-16 bg-gray-100 rounded-xl flex items-center justify-center mx-auto mb-4 hover:bg-gradient-to-r hover:from-primary-500 hover:to-orange-600 hover:text-white transition-all duration-300 transform hover:scale-110">
              <span class="text-2xl" v-html="tool.icon"></span>
            </div>
            <h3 class="text-sm font-medium text-gray-900">{{ tool.name }}</h3>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section-padding gradient-bg text-white">
      <div class="container-max text-center">
        <div class="max-w-4xl mx-auto animate-slide-up">
          <h2 class="text-4xl font-bold font-heading mb-6">
            Ready to Accelerate Your Growth?
          </h2>
          <p class="text-xl text-white/90 mb-8">
            Let's create a comprehensive digital marketing strategy that drives real results for your business.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <router-link to="/contact" class="bg-white text-gray-900 hover:bg-gray-100 font-medium px-8 py-4 rounded-lg transition-colors">
              Start Your Campaign
            </router-link>
            <button class="border-2 border-white text-white hover:bg-white hover:text-gray-900 font-medium px-8 py-4 rounded-lg transition-colors">
              Get Free Audit
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const services = ref([
  {
    icon: '🔍',
    title: 'Search Engine Optimization',
    description: 'Improve your website\'s visibility in search engine results.',
    features: ['Keyword Research', 'On-Page SEO', 'Technical SEO', 'Link Building']
  },
  {
    icon: '📱',
    title: 'Social Media Marketing',
    description: 'Engage your audience across all major social platforms.',
    features: ['Content Creation', 'Community Management', 'Social Advertising', 'Influencer Marketing']
  },
  {
    icon: '💰',
    title: 'Pay-Per-Click Advertising',
    description: 'Targeted advertising campaigns that deliver immediate results.',
    features: ['Google Ads', 'Facebook Ads', 'LinkedIn Ads', 'Campaign Optimization']
  },
  {
    icon: '📝',
    title: 'Content Marketing',
    description: 'Create valuable content that attracts and engages your audience.',
    features: ['Blog Writing', 'Video Content', 'Infographics', 'Content Strategy']
  },
  {
    icon: '📧',
    title: 'Email Marketing',
    description: 'Nurture leads and retain customers with targeted email campaigns.',
    features: ['Email Automation', 'Newsletter Design', 'A/B Testing', 'List Segmentation']
  },
  {
    icon: '📊',
    title: 'Analytics & Reporting',
    description: 'Track performance and optimize campaigns with detailed analytics.',
    features: ['Google Analytics', 'Custom Dashboards', 'ROI Tracking', 'Performance Reports']
  }
])

const strategy = ref([
  {
    title: 'Audit',
    description: 'Comprehensive analysis of your current marketing performance and opportunities.'
  },
  {
    title: 'Strategy',
    description: 'Develop a customized marketing strategy aligned with your business goals.'
  },
  {
    title: 'Execute',
    description: 'Implement campaigns across multiple channels with precision and creativity.'
  },
  {
    title: 'Optimize',
    description: 'Continuously monitor and optimize campaigns for maximum ROI.'
  }
])

const caseStudies = ref([
  {
    company: 'TechStart Inc.',
    industry: 'Technology',
    icon: '💻',
    description: 'Increased online visibility and lead generation for a B2B tech startup.',
    metric1: { value: '+340%', label: 'Organic Traffic' },
    metric2: { value: '+220%', label: 'Qualified Leads' }
  },
  {
    company: 'Fashion Boutique',
    industry: 'E-commerce',
    icon: '👗',
    description: 'Boosted online sales and brand awareness for a fashion retailer.',
    metric1: { value: '+180%', label: 'Online Sales' },
    metric2: { value: '+150%', label: 'Social Followers' }
  },
  {
    company: 'Local Restaurant',
    industry: 'Food & Beverage',
    icon: '🍽️',
    description: 'Improved local visibility and customer acquisition for a restaurant chain.',
    metric1: { value: '+95%', label: 'Foot Traffic' },
    metric2: { value: '+120%', label: 'Online Orders' }
  }
])

const tools = ref([
  { name: 'Google Analytics', icon: '📊' },
  { name: 'Google Ads', icon: '🎯' },
  { name: 'Facebook Ads', icon: '📘' },
  { name: 'HubSpot', icon: '🧡' },
  { name: 'Mailchimp', icon: '📧' },
  { name: 'Hootsuite', icon: '🦉' },
  { name: 'SEMrush', icon: '🔍' },
  { name: 'Canva', icon: '🎨' },
  { name: 'Buffer', icon: '📱' },
  { name: 'Ahrefs', icon: '🔗' },
  { name: 'Hotjar', icon: '🔥' },
  { name: 'Zapier', icon: '⚡' }
])
</script>

<style scoped>
.text-gradient {
  @apply bg-gradient-to-r from-primary-500 to-orange-600 bg-clip-text text-transparent;
}
</style>
