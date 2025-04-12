<template>
    <section
      ref="aboutSection"
      class="min-h-[80vh] flex items-center justify-center px-6 py-20 bg-gradient-to-b from-[#1a1a2e] to-[#0f0f1c]"
    >
      <div class="max-w-3xl text-center backdrop-blur-sm bg-white/10 border border-white/20 rounded-2xl p-10 shadow-2xl">
        <h2 class="text-3xl md:text-5xl font-bold mb-6 text-cyan-300">
          Who We Are
        </h2>
        <p class="text-lg md:text-xl text-gray-300 leading-relaxed">
          At <span class="text-cyan-400 font-semibold">NebulaX</span>, we’re building the next generation of human-AI interfaces. Our mission is to make futuristic tech accessible, beautiful, and intuitive for everyone.
        </p>
      </div>
    </section>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue'
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  
  gsap.registerPlugin(ScrollTrigger)
  
  const aboutSection = ref(null)
  
  onMounted(() => {
    gsap.from(aboutSection.value, {
      scrollTrigger: {
        trigger: aboutSection.value,
        start: 'top 80%',
      },
      opacity: 0,
      y: 50,
      duration: 1,
      ease: 'power2.out',
    })
  })
  </script>
  