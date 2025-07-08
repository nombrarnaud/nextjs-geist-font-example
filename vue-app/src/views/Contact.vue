<template>
  <div class="contact">
    <!-- Hero Section -->
    <section class="relative py-24 bg-gradient-to-br from-primary-600 via-orange-500 to-primary-700 text-white overflow-hidden">
      <div class="absolute inset-0 bg-black/10"></div>
      <div class="container-max relative z-10">
        <div class="text-center animate-slide-up">
          <h1 class="text-5xl font-bold font-heading mb-6">
            {{ $t('contact.title') }}
          </h1>
          <p class="text-xl text-white/90 max-w-3xl mx-auto">
            {{ $t('contact.subtitle') }}
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section class="section-padding bg-gray-50">
      <div class="container-max">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
          <!-- Contact Form -->
          <div class="animate-slide-up">
            <div class="card p-8">
              <h2 class="text-2xl font-bold font-heading text-gray-900 mb-6">
                Send us a Message
              </h2>
              
              <form @submit.prevent="submitForm" class="space-y-6">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                  <div>
                    <label for="firstName" class="block text-sm font-medium text-gray-700 mb-2">
                      First Name *
                    </label>
                    <input
                      type="text"
                      id="firstName"
                      v-model="form.firstName"
                      required
                      class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                      placeholder="John"
                    >
                  </div>
                  <div>
                    <label for="lastName" class="block text-sm font-medium text-gray-700 mb-2">
                      Last Name *
                    </label>
                    <input
                      type="text"
                      id="lastName"
                      v-model="form.lastName"
                      required
                      class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                      placeholder="Doe"
                    >
                  </div>
                </div>

                <div>
                  <label for="email" class="block text-sm font-medium text-gray-700 mb-2">
                    {{ $t('contact.form.email') }} *
                  </label>
                  <input
                    type="email"
                    id="email"
                    v-model="form.email"
                    required
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                    placeholder="john@example.com"
                  >
                </div>

                <div>
                  <label for="phone" class="block text-sm font-medium text-gray-700 mb-2">
                    {{ $t('contact.form.phone') }}
                  </label>
                  <input
                    type="tel"
                    id="phone"
                    v-model="form.phone"
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                    placeholder="+1 (555) 123-4567"
                  >
                </div>

                <div>
                  <label for="company" class="block text-sm font-medium text-gray-700 mb-2">
                    Company
                  </label>
                  <input
                    type="text"
                    id="company"
                    v-model="form.company"
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                    placeholder="Your Company Name"
                  >
                </div>

                <div>
                  <label for="service" class="block text-sm font-medium text-gray-700 mb-2">
                    {{ $t('contact.form.service') }} *
                  </label>
                  <select
                    id="service"
                    v-model="form.service"
                    required
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                  >
                    <option value="">{{ $t('contact.form.selectService') }}</option>
                    <option value="technical-support">{{ $t('nav.technicalSupport') }}</option>
                    <option value="web-mobile-dev">{{ $t('nav.webMobileDev') }}</option>
                    <option value="graphic-design">{{ $t('nav.graphicDesign') }}</option>
                    <option value="digital-marketing">{{ $t('nav.digitalMarketing') }}</option>
                    <option value="cyber-security">{{ $t('nav.cyberSecurity') }}</option>
                    <option value="consultation">General Consultation</option>
                  </select>
                </div>

                <div>
                  <label for="budget" class="block text-sm font-medium text-gray-700 mb-2">
                    Project Budget
                  </label>
                  <select
                    id="budget"
                    v-model="form.budget"
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors"
                  >
                    <option value="">Select Budget Range</option>
                    <option value="under-5k">Under $5,000</option>
                    <option value="5k-15k">$5,000 - $15,000</option>
                    <option value="15k-50k">$15,000 - $50,000</option>
                    <option value="50k-100k">$50,000 - $100,000</option>
                    <option value="over-100k">Over $100,000</option>
                  </select>
                </div>

                <div>
                  <label for="message" class="block text-sm font-medium text-gray-700 mb-2">
                    {{ $t('contact.form.message') }} *
                  </label>
                  <textarea
                    id="message"
                    v-model="form.message"
                    required
                    rows="5"
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-orange-500 focus:border-transparent transition-colors resize-none"
                    placeholder="Tell us about your project requirements..."
                  ></textarea>
                </div>

                <div class="flex items-start">
                  <input
                    type="checkbox"
                    id="privacy"
                    v-model="form.privacy"
                    required
                    class="mt-1 mr-3 w-4 h-4 text-orange-500 border-gray-300 rounded focus:ring-orange-500"
                  >
                  <label for="privacy" class="text-sm text-gray-600">
                    I agree to the <a href="#" class="text-orange-500 hover:text-orange-600">Privacy Policy</a> and 
                    <a href="#" class="text-orange-500 hover:text-orange-600">Terms of Service</a> *
                  </label>
                </div>

                <button
                  type="submit"
                  :disabled="isSubmitting"
                  class="w-full btn-primary disabled:opacity-50 disabled:cursor-not-allowed"
                >
                  <span v-if="!isSubmitting">{{ $t('contact.form.submit') }}</span>
                  <span v-else class="flex items-center justify-center">
                    <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                      <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                      <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                    </svg>
                    Sending...
                  </span>
                </button>
              </form>

              <!-- Success Message -->
              <div v-if="showSuccess" class="mt-6 p-4 bg-green-50 border border-green-200 rounded-lg">
                <div class="flex items-center">
                  <span class="text-green-600 text-xl mr-3">✓</span>
                  <div>
                    <h3 class="text-green-800 font-semibold">Message Sent Successfully!</h3>
                    <p class="text-green-700 text-sm">We'll get back to you within 24 hours.</p>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Contact Information -->
          <div class="animate-slide-up" style="animation-delay: 0.2s;">
            <div class="space-y-8">
              <!-- Contact Info Card -->
              <div class="card p-8">
                <h2 class="text-2xl font-bold font-heading text-gray-900 mb-6">
                  Get in Touch
                </h2>
                
                <div class="space-y-6">
                  <div class="flex items-start">
                    <div class="w-12 h-12 bg-gradient-to-r from-orange-500 to-primary-600 rounded-lg flex items-center justify-center mr-4 flex-shrink-0">
                      <span class="text-white text-xl">📍</span>
                    </div>
                    <div>
                      <h3 class="font-semibold text-gray-900 mb-1">Address</h3>
                      <p class="text-gray-600">{{ $t('contact.info.address') }}</p>
                    </div>
                  </div>

                  <div class="flex items-start">
                    <div class="w-12 h-12 bg-gradient-to-r from-orange-500 to-primary-600 rounded-lg flex items-center justify-center mr-4 flex-shrink-0">
                      <span class="text-white text-xl">📞</span>
                    </div>
                    <div>
                      <h3 class="font-semibold text-gray-900 mb-1">Phone</h3>
                      <p class="text-gray-600">{{ $t('contact.info.phone') }}</p>
                    </div>
                  </div>

                  <div class="flex items-start">
                    <div class="w-12 h-12 bg-gradient-to-r from-orange-500 to-primary-600 rounded-lg flex items-center justify-center mr-4 flex-shrink-0">
                      <span class="text-white text-xl">📧</span>
                    </div>
                    <div>
                      <h3 class="font-semibold text-gray-900 mb-1">Email</h3>
                      <p class="text-gray-600">{{ $t('contact.info.email') }}</p>
                    </div>
                  </div>

                  <div class="flex items-start">
                    <div class="w-12 h-12 bg-gradient-to-r from-orange-500 to-primary-600 rounded-lg flex items-center justify-center mr-4 flex-shrink-0">
                      <span class="text-white text-xl">🕒</span>
                    </div>
                    <div>
                      <h3 class="font-semibold text-gray-900 mb-1">Business Hours</h3>
                      <p class="text-gray-600">{{ $t('contact.info.hours') }}</p>
                    </div>
                  </div>
                </div>
              </div>

              <!-- Quick Links Card -->
              <div class="card p-8">
                <h3 class="text-xl font-bold font-heading text-gray-900 mb-6">
                  Quick Actions
                </h3>
                
                <div class="space-y-4">
                  <a href="tel:+15551234567" class="flex items-center p-4 bg-green-50 rounded-lg hover:bg-green-100 transition-colors">
                    <span class="text-green-600 text-xl mr-3">📞</span>
                    <div>
                      <div class="font-semibold text-green-800">Call Now</div>
                      <div class="text-green-600 text-sm">For immediate assistance</div>
                    </div>
                  </a>

                  <a href="mailto:info@wendyincorporated.com" class="flex items-center p-4 bg-blue-50 rounded-lg hover:bg-blue-100 transition-colors">
                    <span class="text-blue-600 text-xl mr-3">📧</span>
                    <div>
                      <div class="font-semibold text-blue-800">Send Email</div>
                      <div class="text-blue-600 text-sm">Get a detailed response</div>
                    </div>
                  </a>

                  <button class="w-full flex items-center p-4 bg-orange-50 rounded-lg hover:bg-orange-100 transition-colors">
                    <span class="text-orange-600 text-xl mr-3">📅</span>
                    <div class="text-left">
                      <div class="font-semibold text-orange-800">Schedule Meeting</div>
                      <div class="text-orange-600 text-sm">Book a consultation</div>
                    </div>
                  </button>
                </div>
              </div>

              <!-- Emergency Contact -->
              <div class="card p-8 bg-red-50 border-red-200">
                <h3 class="text-xl font-bold font-heading text-red-800 mb-4">
                  Emergency Support
                </h3>
                <p class="text-red-700 mb-4">
                  For critical security incidents or system emergencies
                </p>
                <a href="tel:+15551234567" class="inline-flex items-center bg-red-600 hover:bg-red-700 text-white font-medium px-6 py-3 rounded-lg transition-colors">
                  <span class="mr-2">🚨</span>
                  Call Emergency Line
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Map Section -->
    <section class="py-16 bg-white">
      <div class="container-max">
        <div class="text-center mb-12 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Visit Our Office
          </h2>
          <p class="text-xl text-gray-600">
            We'd love to meet you in person
          </p>
        </div>

        <div class="animate-slide-up" style="animation-delay: 0.2s;">
          <div class="bg-gray-200 rounded-xl h-96 flex items-center justify-center">
            <div class="text-center">
              <span class="text-6xl mb-4 block">🗺️</span>
              <h3 class="text-xl font-semibold text-gray-700 mb-2">Interactive Map</h3>
              <p class="text-gray-600">Map integration would be implemented here</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="section-padding bg-gray-50">
      <div class="container-max">
        <div class="text-center mb-16 animate-slide-up">
          <h2 class="text-4xl font-bold font-heading text-gray-900 mb-4">
            Frequently Asked Questions
          </h2>
          <p class="text-xl text-gray-600 max-w-3xl mx-auto">
            Quick answers to common questions
          </p>
        </div>

        <div class="max-w-4xl mx-auto">
          <div class="space-y-6">
            <div v-for="(faq, index) in faqs" :key="index" 
                 class="card p-6 animate-slide-up" 
                 :style="{ animationDelay: `${index * 0.1}s` }">
              <button 
                @click="toggleFaq(index)"
                class="w-full text-left flex items-center justify-between"
              >
                <h3 class="text-lg font-semibold text-gray-900">{{ faq.question }}</h3>
                <span class="text-orange-500 text-xl transition-transform duration-200" 
                      :class="{ 'rotate-45': faq.isOpen }">+</span>
              </button>
              <div v-show="faq.isOpen" class="mt-4 text-gray-600">
                {{ faq.answer }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'

const form = reactive({
  firstName: '',
  lastName: '',
  email: '',
  phone: '',
  company: '',
  service: '',
  budget: '',
  message: '',
  privacy: false
})

const isSubmitting = ref(false)
const showSuccess = ref(false)

const faqs = ref([
  {
    question: 'How quickly can you start working on my project?',
    answer: 'We typically begin new projects within 1-2 weeks of contract signing, depending on our current workload and project complexity.',
    isOpen: false
  },
  {
    question: 'Do you offer ongoing support after project completion?',
    answer: 'Yes, we provide various support packages including maintenance, updates, and technical support to ensure your solution continues to perform optimally.',
    isOpen: false
  },
  {
    question: 'What is your typical project timeline?',
    answer: 'Project timelines vary based on scope and complexity. Simple websites may take 2-4 weeks, while complex applications can take 3-6 months or more.',
    isOpen: false
  },
  {
    question: 'Do you work with international clients?',
    answer: 'Absolutely! We work with clients worldwide and have experience managing projects across different time zones and cultural contexts.',
    isOpen: false
  },
  {
    question: 'What payment methods do you accept?',
    answer: 'We accept various payment methods including bank transfers, credit cards, and digital payment platforms. Payment terms are typically structured in milestones.',
    isOpen: false
  }
])

const submitForm = async () => {
  isSubmitting.value = true
  
  // Simulate form submission
  await new Promise(resolve => setTimeout(resolve, 2000))
  
  // Reset form
  Object.keys(form).forEach(key => {
    if (key === 'privacy') {
      form[key] = false
    } else {
      form[key] = ''
    }
  })
  
  isSubmitting.value = false
  showSuccess.value = true
  
  // Hide success message after 5 seconds
  setTimeout(() => {
    showSuccess.value = false
  }, 5000)
}

const toggleFaq = (index: number) => {
  faqs.value[index].isOpen = !faqs.value[index].isOpen
}
</script>

<style scoped>
/* Additional styles if needed */
</style>
