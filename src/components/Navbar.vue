<template>
  <nav
    class="fixed w-full z-50 transition-all duration-500"
    :class="{
      'bg-white/95 backdrop-blur-lg shadow-lg py-3 border-b border-gray-200':
        scrolled,
      'py-5': !scrolled,
    }"
  >
    <div class="container mx-auto px-6 flex justify-between items-center">
      <!-- Logo -->
      <div class="flex items-center space-x-3 group cursor-pointer">
        <div class="relative">
          <svg
            class="w-8 h-8 text-indigo-600 transition-transform duration-300 group-hover:rotate-12 group-hover:scale-110"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M7 16a5 5 0 01-.674-9.953 5.002 5.002 0 019.348 0A5 5 0 0117 16"
              stroke="currentColor"
              stroke-width="2.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
          <div
            class="absolute -inset-1 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-full opacity-0 group-hover:opacity-20 blur transition-opacity duration-300"
          ></div>
        </div>
        <span
          class="text-2xl font-bold bg-gradient-to-r from-indigo-600 to-purple-600 bg-clip-text text-transparent"
        >
          Cloudifice
        </span>
      </div>

      <!-- Desktop Navigation -->
      <div class="hidden md:flex space-x-8">
        <a
          v-for="link in links"
          :key="link.name"
          :href="link.href"
          class="nav-link group relative font-medium transition-all duration-300"
          :class="
            scrolled
              ? 'text-gray-700 hover:text-indigo-600'
              : 'text-white hover:text-indigo-300'
          "
        >
          {{ link.name }}
          <span class="nav-underline"></span>
        </a>
      </div>

      <!-- Desktop CTA Buttons -->
      <div class="hidden md:flex items-center space-x-4">
        <button
          @click="routeToLoginPage"
          :class="
            scrolled
              ? 'text-gray-700 hover:text-indigo-600'
              : 'text-white hover:text-indigo-300'
          "
          class="px-4 py-2 rounded-lg font-medium transition-all duration-300 hover:bg-white/10"
        >
          Login
        </button>
        <button @click="routeToSignupPage" class="cta-button">
          Get Started
        </button>
      </div>

      <!-- Mobile Menu Button -->
      <button
        @click="mobileMenuOpen = !mobileMenuOpen"
        class="md:hidden p-2 rounded-lg transition-all duration-300 hover:bg-white/10"
        :class="scrolled ? 'text-gray-800' : 'text-white'"
      >
        <svg
          class="w-6 h-6 transition-transform duration-300"
          :class="{ 'rotate-90': mobileMenuOpen }"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            :d="
              mobileMenuOpen ? 'M6 18L18 6M6 6l12 12' : 'M4 6h16M4 12h16m-7 6h7'
            "
          ></path>
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <div
      class="md:hidden transition-all duration-500 ease-in-out overflow-hidden"
      :class="{
        'max-h-96 opacity-100': mobileMenuOpen,
        'max-h-0 opacity-0': !mobileMenuOpen,
      }"
    >
      <div
        class="bg-white/95 backdrop-blur-lg border-t border-gray-200 px-6 py-4 space-y-4"
        v-if="scrolled || mobileMenuOpen"
      >
        <a
          v-for="link in links"
          :key="link.name"
          :href="link.href"
          @click="mobileMenuOpen = false"
          class="block py-2 text-gray-700 hover:text-indigo-600 font-medium transition-colors duration-300"
        >
          {{ link.name }}
        </a>
        <div class="pt-4 border-t border-gray-200 space-y-3">
          <button
            class="w-full py-2 text-gray-700 hover:text-indigo-600 font-medium transition-colors duration-300"
          >
            Login
          </button>
          <button
            class="w-full px-6 py-3 rounded-lg bg-gradient-to-r from-indigo-600 to-purple-600 text-white font-medium hover:shadow-lg hover:shadow-indigo-500/30 transition-all duration-300"
          >
            Get Started
          </button>
        </div>
      </div>

      <!-- Mobile Menu for Non-scrolled State -->
      <div
        class="bg-black/20 backdrop-blur-lg border-t border-white/20 px-6 py-4 space-y-4"
        v-else
      >
        <a
          v-for="link in links"
          :key="link.name"
          :href="link.href"
          @click="mobileMenuOpen = false"
          class="block py-2 text-white hover:text-indigo-300 font-medium transition-colors duration-300"
        >
          {{ link.name }}
        </a>
        <div class="pt-4 border-t border-white/20 space-y-3">
          <button
            class="w-full py-2 text-white hover:text-indigo-300 font-medium transition-colors duration-300"
          >
            Login
          </button>
          <button
            class="w-full px-6 py-3 rounded-lg bg-gradient-to-r from-indigo-600 to-purple-600 text-white font-medium hover:shadow-lg hover:shadow-indigo-500/30 transition-all duration-300"
          >
            Get Started
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const scrolled = ref(false);
const mobileMenuOpen = ref(false);

const links = [
  { name: 'Features', href: '#features' },
  { name: 'Demo', href: '#demo' },
  { name: 'Pricing', href: '#pricing' },
  { name: 'Contact', href: '#contact' },
];

const handleScroll = () => {
  scrolled.value = window.scrollY > 20;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

function routeToLoginPage() {
  window.open('https://cloudifice.eyouel-kibret.dev.et/login', '_blank');
}
function routeToSignupPage() {
  window.open('https://cloudifice.eyouel-kibret.dev.et/signup', '_blank');
}
</script>

<style scoped>
/* Navigation Link Underline Effect */
.nav-link {
  position: relative;
}

.nav-underline {
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(to right, #6366f1, #8b5cf6);
  transition: width 0.3s ease;
}

.nav-link:hover .nav-underline {
  width: 100%;
}

/* CTA Button */
.cta-button {
  @apply px-6 py-2.5 rounded-lg bg-gradient-to-r from-indigo-600 to-purple-600 text-white font-medium transition-all duration-300 hover:shadow-lg hover:shadow-indigo-500/30 hover:-translate-y-0.5 hover:scale-105;
}

.cta-button:hover {
  box-shadow: 0 10px 25px -5px rgba(99, 102, 241, 0.4);
}
</style>
