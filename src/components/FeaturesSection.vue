<template>
    <section
      ref="featuresSection"
      class="min-h-screen px-6 py-20 bg-gradient-to-b from-[#0f0f1c] to-[#101019] text-white flex flex-col items-center"
    >
      <h2 class="text-3xl md:text-5xl font-bold text-cyan-300 mb-12 text-center">
        Our Key Features
      </h2>
  
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10 max-w-6xl w-full"
      >
        <div
          v-for="(feature, index) in features"
          :key="index"
          :ref="el => featureRefs[index] = el"
          class="glass-card p-6 rounded-2xl border border-white/20 backdrop-blur-md bg-white/10 shadow-2xl text-center transition-transform duration-300 hover:scale-105"
        >
          <div class="text-4xl mb-4">{{ feature.icon }}</div>
          <h3 class="text-xl font-semibold text-cyan-300 mb-2">{{ feature.title }}</h3>
          <p class="text-gray-300">{{ feature.desc }}</p>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue'
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  
  gsap.registerPlugin(ScrollTrigger)
  
  const features = [
    {
      icon: '🚀',
      title: 'Blazing Performance',
      desc: 'Experience lightning-fast load times and seamless transitions.',
    },
    {
      icon: '🧠',
      title: 'AI-Powered UX',
      desc: 'Smart, adaptive user interfaces driven by machine learning.',
    },
    {
      icon: '🔒',
      title: 'Enterprise-Grade Security',
      desc: 'Protect your data with cutting-edge encryption and practices.',
    },
    {
      icon: '🌐',
      title: 'Global Scalability',
      desc: 'Built to perform across regions, networks, and user bases.',
    },
    {
      icon: '💡',
      title: 'Innovative Design',
      desc: 'Futuristic visuals and intuitive layouts meet function.',
    },
    {
      icon: '📈',
      title: 'Analytics Built-In',
      desc: 'Real-time tracking and insights to fuel your growth.',
    },
  ]
  
  const featureRefs = []
  
  onMounted(() => {
    featureRefs.forEach((el, i) => {
      gsap.from(el, {
        scrollTrigger: {
          trigger: el,
          start: 'top 85%',
        },
        opacity: 0,
        scale: 0.8,
        duration: 0.6,
        delay: i * 0.1,
        ease: 'power2.out',
      })
    })
  })
  </script>
  
  <style scoped>
  .glass-card {
    backdrop-filter: blur(12px);
  }
  </style>
  