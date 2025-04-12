<template>
    <section
      ref="ctaSection"
      class="min-h-[60vh] flex flex-col items-center justify-center px-6 py-24 bg-gradient-to-b from-[#101019] to-[#0f0f1c] text-center relative"
    >
      <div
        class="max-w-2xl backdrop-blur-md bg-white/10 border border-white/20 rounded-2xl p-10 shadow-2xl"
      >
        <h2 class="text-3xl md:text-5xl font-extrabold mb-6 text-cyan-300 leading-tight">
          Ready to Build the Future?
        </h2>
        <p class="text-lg md:text-xl text-gray-300 mb-8">
          Join the revolution with NebulaX — futuristic interfaces built for tomorrow.
        </p>
        <button
          class="px-8 py-4 bg-cyan-500/20 hover:bg-cyan-400/30 text-cyan-300 font-semibold text-lg rounded-xl border border-cyan-300/30 shadow-lg backdrop-blur-sm transition-all duration-300"
        >
          Join Waitlist 🚀
        </button>
      </div>
    </section>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue'
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  
  gsap.registerPlugin(ScrollTrigger)
  
  const ctaSection = ref(null)
  
  onMounted(() => {
    gsap.from(ctaSection.value, {
      scrollTrigger: {
        trigger: ctaSection.value,
        start: 'top 85%',
      },
      opacity: 0,
      scale: 0.95,
      duration: 1,
      ease: 'power2.out',
    })
  })
  </script>
  