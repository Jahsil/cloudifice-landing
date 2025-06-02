<template>
  <section class="relative py-20 overflow-hidden">
    <div class="absolute inset-0 overflow-hidden">
      <div
        class="absolute inset-0 bg-gradient-to-r from-indigo-500 to-purple-600 opacity-90"
      ></div>
      <div
        class="absolute inset-0 bg-[url('@/assets/images/grid.jpg')] bg-center [mask-image:linear-gradient(180deg,white,rgba(255,255,255,0))]"
      ></div>
      <div
        v-for="i in 15"
        :key="i"
        class="absolute rounded-full bg-white opacity-10"
        :style="{
          width: `${Math.random() * 100 + 50}px`,
          height: `${Math.random() * 100 + 50}px`,
          top: `${Math.random() * 100}%`,
          left: `${Math.random() * 100}%`,
          animation: `float ${Math.random() * 15 + 10}s linear infinite`,
          animationDelay: `${Math.random() * 5}s`,
        }"
      ></div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <div class="text-center">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-6">
          Ready to Transform Your File Storage?
        </h2>
        <p class="text-xl text-indigo-100 max-w-2xl mx-auto mb-8">
          Join thousands of teams who trust Cloudifice for their distributed
          storage needs.
        </p>
        <div
          class="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-4"
        >
          <button
            class="px-8 py-4 bg-white text-indigo-600 font-semibold rounded-lg hover:bg-gray-100 transition transform hover:-translate-y-1 hover:scale-105"
          >
            Start Free 14-Day Trial
          </button>
          <button
            class="px-8 py-4 border-2 border-white text-white font-semibold rounded-lg hover:bg-white/10 transition"
          >
            Schedule a Demo
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
@keyframes float {
  0% {
    transform: translateY(0) translateX(0) rotate(0deg);
    opacity: 1;
  }
  50% {
    transform: translateY(-100px) translateX(50px) rotate(180deg);
    opacity: 0.8;
  }
  100% {
    transform: translateY(0) translateX(0) rotate(360deg);
    opacity: 1;
  }
}
</style>
