<template>
  <div class="font-sans text-gray-900 antialiased">
    <Navbar />

    <main>
      <Hero class="fade-in" />
      <Features class="fade-in delay-100" />
      <DemoVideo class="fade-in delay-200" />
      <Pricing class="fade-in delay-300" />
      <Testimonials />
      <CTA />
    </main>

    <Footer />
  </div>
  <div>
    <p class="text-red-300">Hello</p>
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import Features from './components/Features.vue';
import DemoVideo from './components/DemoVideo.vue';
import Pricing from './components/Pricing.vue';
import Testimonials from './components/Testimonials.vue';
import CTA from './components/CTA.vue';
import Footer from './components/Footer.vue';

import { onMounted } from 'vue';

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('animate');
        }
      });
    },
    {
      threshold: 0.1,
    },
  );

  document.querySelectorAll('.feature-card').forEach((card) => {
    observer.observe(card);
  });
});
</script>
