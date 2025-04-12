<template>
    <footer class="bg-[#0f0f1c] py-10 px-6 text-center text-gray-400 border-t border-white/10">
      <div class="mb-4 flex justify-center gap-6">
        <a
          v-for="(link, index) in socialLinks"
          :key="index"
          :href="link.href"
          target="_blank"
          rel="noopener noreferrer"
          class="text-xl hover:text-cyan-400 transition-colors duration-300"
        >
          <span v-html="link.icon"></span>
        </a>
      </div>
      <p class="text-sm text-gray-500">
        © {{ new Date().getFullYear() }} NebulaX. Built with 💙 by Shailendra.
      </p>
    </footer>
  </template>
  
  <script setup>
  const socialLinks = [
    {
      href: "https://github.com/",
      icon: `<i class="fab fa-github"></i>`,
    },
    {
      href: "https://twitter.com/",
      icon: `<i class="fab fa-twitter"></i>`,
    },
    {
      href: "https://linkedin.com/",
      icon: `<i class="fab fa-linkedin"></i>`,
    },
  ]
  </script>
  
  <!-- Ensure font-awesome is added in index.html -->
  <!-- You can skip this if you're using your own SVGs -->
  <!-- Add in your public/index.html head tag: -->
  <!-- <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" /> -->
  