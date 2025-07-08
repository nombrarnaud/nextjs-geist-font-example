<template>
  <div class="cyber-security">
    <!-- Hero Section -->
    <section class="relative py-24 bg-gradient-to-br from-gray-900 via-primary-800 to-orange-700 text-white overflow-hidden">
      <div class="absolute inset-0 bg-black/20"></div>
      <div class="container-max relative z-10">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="animate-slide-up">
            <h1 class="text-5xl font-bold font-heading mb-6">
              {{ $t('services.cyberSecurity.title') }}
            </h1>
            <p class="text-xl text-white/90 mb-8">
              {{ $t('services.cyberSecurity.subtitle') }}
            </p>
            <p class="text-lg text-white/80 mb-8">
              {{ $t('services.cyberSecurity.description') }}
            </p>
            <router-link to="/contact" class="btn-secondary">
              Secure Your Business
            </router-link>
          </div>
          
          <!-- Illustration -->
          <div class="relative animate-fade-in" style="animation-delay: 0.5s;">
            <div class="relative w-full h-96">
              <!-- Security Dashboard -->
              <div class="absolute inset-0 bg-white/10 backdrop-blur-sm rounded-2xl p-6 border border-white/20">
                <div class="bg-gray-900 rounded-lg p-4 h-full border border-green-500/30">
                  <div class="flex items-center justify-between mb-4">
                    <h3 class="text-green-400 font-semibold">Security Monitor</h3>
                    <div class="flex items-center space-x-2">
                      <div class="w-3 h-3 bg-green-400 rounded-full animate-pulse"></div>
                      <span class="text-green-400 text-xs">SECURE</span>
                    </div>
                  </div>
                  
                  <!-- Security Status -->
                  <div class="space-y-3">
                    <div class="flex items-center justify-between">
                      <span class="text-gray-300 text-sm">Firewall Status</span>
                      <span class="text-green-400 text-sm">✓ Active</span>
                    </div>
                    <div class="flex items-center justify-between">
                      <span class="text-gray-300 text-sm">Threat Detection</span>
                      <span class="text-green-400 text-sm">✓ Online</span>
                    </div>
                    <div class="flex items-center justify-between">
                      <span class="text-gray-300 text-sm">Data Encryption</span>
                      <span class="text-green-400 text-sm">✓ Enabled</span>
                    </div>
                    <div class="flex items-center justify-between">
                      <span class="text-gray-300 text-sm">Access Control</span>
                      <span class="text-green-400 text-sm">✓ Secured</span>
                    </div>
                  </div>
                  
                  <!-- Threat Counter -->
                  <div class="mt-6 p-3 bg-red-900/30 rounded border border-red-500/30">
                    <div class="text-red-400 text-xs mb-1">Threats Blocked Today</div>
                    <div class="text-red-400 text-2xl font-bold">247</div>
                  </div>
                </div>
              </div>
              
              <!-- Floating Security Icons -->
              <div class="absolute -top-4 -right-4 w-16 h-16 bg-green-500 rounded-xl shadow-xl flex items-center justify-center animate-float">
                <span class="text-white text-2xl">🔒</span>
              </div>
              <div class="absolute -bottom-4 -left-4 w-14 h-14 bg-red-500 rounded-xl shadow-xl flex items-center justify-center animate-float" style="animation-delay: 2s;">
                <span class="text-white text-xl">🛡️</span>
              </div>
              <div class="absolute top-1/2 -right-8 w-12 h-12 bg-orange-500 rounded-full shadow-xl flex items-center justify-center animate-float" style="animation-delay: 4s;">
                <span class="text-white text-lg">⚠️</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Threat Landscape -->
    <section class="section-padding bg-red-50">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Current Threat Landscape
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Understanding the cybersecurity challenges facing businesses today
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(threat, index) in threats" :key="index" 
               class="bg-white rounded-xl p-6 shadow-lg animate-slide-up" 
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="w-16 h-16 bg-red-100 rounded-xl flex items-center justify-center mb-4">
              <span class="text-red-600 text-2xl" v-html="threat.icon"></span>
            </div>
            <h3 class="text-lg font-semibold text-gray-900 mb-2">{{ threat.title }}</h3>
            <p class="text-gray-600 text-sm mb-3">{{ threat.description }}</p>
            <div class="text-red-600 font-bold text-2xl">{{ threat.stat }}</div>
            <div class="text-gray-500 text-xs">{{ threat.statLabel }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="section-padding bg-white">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Our Security Services
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Comprehensive cybersecurity solutions to protect your business
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(service, index) in services" :key="index" 
               class="card p-8 animate-slide-up" 
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="w-16 h-16 bg-gradient-to-r from-gray-700 to-primary-600 rounded-xl flex items-center justify-center mb-6">
              <span class="text-white text-2xl" v-html="service.icon"></span>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 mb-4">{{ service.title }}</h3>
            <p class="text-gray-600 mb-4">{{ service.description }}</p>
            <ul class="space-y-2">
              <li v-for="feature in service.features" :key="feature" class="flex items-center text-sm text-gray-600">
                <span class="w-2 h-2 bg-green-500 rounded-full mr-3"></span>
                {{ feature }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Security Framework -->
    <section class="section-padding bg-gray-50">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Our Security Framework
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Multi-layered approach to comprehensive cybersecurity
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-8">
          <div v-for="(layer, index) in securityLayers" :key="index" 
               class="text-center animate-slide-up" 
               :style="{ animationDelay: `${index * 0.2}s` }">
            <div class="w-20 h-20 bg-gradient-to-r from-gray-700 to-primary-600 rounded-full flex items-center justify-center mx-auto mb-6">
              <span class="text-white text-2xl" v-html="layer.icon"></span>
            </div>
            <h3 class="text-lg font-semibold text-gray-900 mb-4">{{ layer.title }}</h3>
            <p class="text-gray-600 text-sm">{{ layer.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Compliance Standards -->
    <section class="section-padding bg-white">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Compliance & Standards
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            We help you meet industry compliance requirements
          </p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-8">
          <div v-for="(standard, index) in complianceStandards" :key="index" 
               class="text-center animate-slide-up" 
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="w-16 h-16 bg-gray-100 rounded-xl flex items-center justify-center mx-auto mb-4 hover:bg-gradient-to-r hover:from-gray-700 hover:to-primary-600 hover:text-white transition-all duration-300 transform hover:scale-110">
              <span class="text-2xl font-bold">{{ standard.name }}</span>
            </div>
            <h3 class="text-sm font-medium text-gray-900">{{ standard.fullName }}</h3>
          </div>
        </div>
      </div>
    </section>

    <!-- Security Assessment -->
    <section class="section-padding bg-gray-900 text-white">
      <div class="container-max">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="animate-slide-up">
            <h2 class="text-4xl font-bold font-heading mb-6">
              Free Security Assessment
            </h2>
            <p class="text-xl text-white/90 mb-8">
              Get a comprehensive evaluation of your current security posture
            </p>
            <ul class="space-y-4 mb-8">
              <li v-for="benefit in assessmentBenefits" :key="benefit" class="flex items-center">
                <span class="w-6 h-6 bg-green-500 rounded-full flex items-center justify-center mr-4">
                  <span class="text-white text-sm">✓</span>
                </span>
                <span class="text-white/90">{{ benefit }}</span>
              </li>
            </ul>
            <router-link to="/contact" class="bg-orange-500 hover:bg-orange-600 text-white font-medium px-8 py-4 rounded-lg transition-colors">
              Request Free Assessment
            </router-link>
          </div>
          
          <div class="relative animate-fade-in" style="animation-delay: 0.5s;">
            <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20">
              <h3 class="text-xl font-semibold mb-6">Assessment Includes:</h3>
              <div class="space-y-4">
                <div class="flex items-center justify-between p-3 bg-white/5 rounded-lg">
                  <span>Network Vulnerability Scan</span>
                  <span class="text-green-400">✓</span>
                </div>
                <div class="flex items-center justify-between p-3 bg-white/5 rounded-lg">
                  <span>Security Policy Review</span>
                  <span class="text-green-400">✓</span>
                </div>
                <div class="flex items-center justify-between p-3 bg-white/5 rounded-lg">
                  <span>Compliance Gap Analysis</span>
                  <span class="text-green-400">✓</span>
                </div>
                <div class="flex items-center justify-between p-3 bg-white/5 rounded-lg">
                  <span>Risk Assessment Report</span>
                  <span class="text-green-400">✓</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section-padding gradient-bg text-white">
      <div class="container-max text-center">
        <div class="max-w-4xl mx-auto animate-slide-up">
          <h2 class="text-4xl font-bold font-heading mb-6">
            Don't Wait for a Breach
          </h2>
          <p class="text-xl text-white/90 mb-8">
            Protect your business with our comprehensive cybersecurity solutions. Contact us today for a consultation.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <router-link to="/contact" class="bg-white text-gray-900 hover:bg-gray-100 font-medium px-8 py-4 rounded-lg transition-colors">
              Get Protected Now
            </router-link>
            <button class="border-2 border-white text-white hover:bg-white hover:text-gray-900 font-medium px-8 py-4 rounded-lg transition-colors">
              Emergency Response: 24/7
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const threats = ref([
  {
    icon: '🦠',
    title: 'Malware Attacks',
    description: 'Malicious software designed to damage or gain unauthorized access to systems.',
    stat: '5.6B',
    statLabel: 'attacks in 2023'
  },
  {
    icon: '🎣',
    title: 'Phishing Scams',
    description: 'Fraudulent attempts to obtain sensitive information through deceptive emails.',
    stat: '83%',
    statLabel: 'of organizations targeted'
  },
  {
    icon: '💰',
    title: 'Ransomware',
    description: 'Malware that encrypts data and demands payment for decryption keys.',
    stat: '$4.45M',
    statLabel: 'average breach cost'
  },
  {
    icon: '👤',
    title: 'Insider Threats',
    description: 'Security risks that come from people within the organization.',
    stat: '34%',
    statLabel: 'of breaches involve insiders'
  }
])

const services = ref([
  {
    icon: '🔍',
    title: 'Security Audits & Assessments',
    description: 'Comprehensive evaluation of your security infrastructure and policies.',
    features: ['Vulnerability Assessment', 'Penetration Testing', 'Risk Analysis', 'Compliance Review']
  },
  {
    icon: '🚨',
    title: 'Threat Detection & Response',
    description: '24/7 monitoring and rapid response to security incidents.',
    features: ['Real-time Monitoring', 'Incident Response', 'Threat Intelligence', 'Forensic Analysis']
  },
  {
    icon: '🔐',
    title: 'Data Protection & Encryption',
    description: 'Secure your sensitive data with advanced encryption technologies.',
    features: ['Data Encryption', 'Backup Solutions', 'Access Controls', 'Data Loss Prevention']
  },
  {
    icon: '🌐',
    title: 'Network Security',
    description: 'Protect your network infrastructure from cyber threats.',
    features: ['Firewall Management', 'VPN Solutions', 'Network Monitoring', 'Intrusion Prevention']
  },
  {
    icon: '📋',
    title: 'Compliance Management',
    description: 'Ensure your organization meets industry regulatory requirements.',
    features: ['GDPR Compliance', 'HIPAA Compliance', 'SOX Compliance', 'ISO 27001']
  },
  {
    icon: '🎓',
    title: 'Security Training',
    description: 'Educate your team on cybersecurity best practices.',
    features: ['Phishing Simulation', 'Security Awareness', 'Policy Training', 'Incident Response Training']
  }
])

const securityLayers = ref([
  {
    icon: '👥',
    title: 'People',
    description: 'Security awareness training and access management'
  },
  {
    icon: '🔧',
    title: 'Process',
    description: 'Security policies, procedures, and incident response'
  },
  {
    icon: '💻',
    title: 'Technology',
    description: 'Security tools, monitoring, and threat detection'
  },
  {
    icon: '🏢',
    title: 'Physical',
    description: 'Physical security controls and environmental protection'
  },
  {
    icon: '📊',
    title: 'Governance',
    description: 'Risk management, compliance, and security oversight'
  }
])

const complianceStandards = ref([
  { name: 'GDPR', fullName: 'General Data Protection Regulation' },
  { name: 'HIPAA', fullName: 'Health Insurance Portability' },
  { name: 'SOX', fullName: 'Sarbanes-Oxley Act' },
  { name: 'PCI', fullName: 'Payment Card Industry' },
  { name: 'ISO', fullName: 'ISO 27001 Standard' },
  { name: 'NIST', fullName: 'NIST Cybersecurity Framework' }
])

const assessmentBenefits = ref([
  'Identify security vulnerabilities and risks',
  'Receive detailed remediation recommendations',
  'Understand your compliance status',
  'Get a prioritized action plan',
  'No obligation consultation included'
])
</script>

<style scoped>
.text-gradient {
  @apply bg-gradient-to-r from-gray-700 to-primary-600 bg-clip-text text-transparent;
}
</style>
