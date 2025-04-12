<template>
    <section class="min-h-screen flex flex-col justify-center items-center bg-gradient-to-b from-[#0f0f1c] to-[#1a1a2e] text-white px-4 relative overflow-hidden">
      <div
        ref="heroContainer"
        class="backdrop-blur-sm bg-white/10 border border-white/20 rounded-2xl p-10 max-w-3xl w-full text-center shadow-2xl"
      >
        <h1 class="text-4xl md:text-6xl font-extrabold tracking-tight mb-4">
          Welcome to <span class="text-cyan-400">NebulaX</span>
        </h1>
        <p class="text-lg md:text-xl text-gray-300 mb-8">
          The Future of Innovation Starts Here
        </p>
        <button
          class="px-6 py-3 rounded-xl bg-cyan-500/20 hover:bg-cyan-500/30 text-cyan-300 font-semibold transition-all duration-300 backdrop-blur-xs border border-cyan-300/20 shadow-lg"
        >
          Get Started
        </button>
      </div>
  
      <!-- Floating Element (just for visual flair) -->
      <img
        ref="floatingOrb"
        src="https://cdn-icons-png.flaticon.com/512/616/616408.png"
        alt="orb"
        class="w-14 h-14 absolute top-16 right-16 opacity-80"
      />
    </section>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue'
  import { gsap } from 'gsap'
  
  const heroContainer = ref(null)
  const floatingOrb = ref(null)
  
  onMounted(() => {
    // Floating animation for orb
    gsap.to(floatingOrb.value, {
      y: -20,
      duration: 2,
      repeat: -1,
      yoyo: true,
      ease: 'power1.inOut',
    })
  
    // Fade-in hero section
    gsap.from(heroContainer.value, {
      opacity: 0,
      scale: 0.95,
      duration: 1,
      ease: 'power2.out',
    })
  })
  </script>