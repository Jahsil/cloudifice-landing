<template>
  <section id="testimonials" class="py-20 bg-white">
    <div class="container mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Trusted by Teams Worldwide
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Join thousands of satisfied customers who switched to Cloudifice
        </p>
      </div>

      <div class="relative max-w-4xl mx-auto">
        <div class="overflow-hidden">
          <div
            class="flex transition-transform duration-500 ease-in-out"
            :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
          >
            <div
              v-for="(testimonial, index) in testimonials"
              :key="index"
              class="w-full flex-shrink-0 px-4"
            >
              <div class="bg-gray-50 rounded-xl p-8 md:p-10">
                <div class="flex items-center mb-6">
                  <div class="w-12 h-12 rounded-full overflow-hidden mr-4">
                    <img
                      :src="testimonial.avatar"
                      :alt="testimonial.name"
                      class="w-full h-full object-cover"
                    />
                  </div>
                  <div>
                    <h4 class="font-semibold text-gray-900">
                      {{ testimonial.name }}
                    </h4>
                    <p class="text-gray-600">
                      {{ testimonial.position }}, {{ testimonial.company }}
                    </p>
                  </div>
                </div>
                <p class="text-lg text-gray-700 italic">
                  "{{ testimonial.quote }}"
                </p>
                <div class="mt-6 flex items-center">
                  <div class="flex">
                    <svg
                      v-for="i in 5"
                      :key="i"
                      class="w-5 h-5"
                      :class="{
                        'text-yellow-400': i <= testimonial.rating,
                        'text-gray-300': i > testimonial.rating,
                      }"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                      ></path>
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <button
          @click="prevSlide"
          class="absolute left-0 top-1/2 transform -translate-y-1/2 -translate-x-4 bg-white p-2 rounded-full shadow-md hover:bg-gray-100 focus:outline-none"
        >
          <svg
            class="w-6 h-6 text-gray-600"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 19l-7-7 7-7"
            ></path>
          </svg>
        </button>
        <button
          @click="nextSlide"
          class="absolute right-0 top-1/2 transform -translate-y-1/2 translate-x-4 bg-white p-2 rounded-full shadow-md hover:bg-gray-100 focus:outline-none"
        >
          <svg
            class="w-6 h-6 text-gray-600"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5l7 7-7 7"
            ></path>
          </svg>
        </button>

        <div class="flex justify-center mt-8 space-x-2">
          <button
            v-for="i in testimonials.length"
            :key="i"
            @click="currentSlide = i - 1"
            class="w-3 h-3 rounded-full"
            :class="{
              'bg-indigo-600': currentSlide === i - 1,
              'bg-gray-300': currentSlide !== i - 1,
            }"
          ></button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const currentSlide = ref(0);

const testimonials = [
  {
    name: 'Sarah Johnson',
    position: 'CTO',
    company: 'TechCorp',
    quote:
      'Cloudifice has transformed how we handle our distributed file storage. The self-hosting options gave us complete control while maintaining ease of use.',
    rating: 5,
    avatar: 'https://randomuser.me/api/portraits/women/44.jpg',
  },
  {
    name: 'Michael Chen',
    position: 'Lead Developer',
    company: 'InnovateSoft',
    quote:
      "The cluster management features are incredibly robust. We've scaled to 15 nodes with zero downtime during the expansion process.",
    rating: 5,
    avatar: 'https://randomuser.me/api/portraits/men/32.jpg',
  },
  {
    name: 'Emma Rodriguez',
    position: 'Product Manager',
    company: 'DesignHub',
    quote:
      "Our team loves the built-in chat feature. It's eliminated the need for separate communication tools when collaborating on files.",
    rating: 4,
    avatar: 'https://randomuser.me/api/portraits/women/63.jpg',
  },
];

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % testimonials.length;
};

const prevSlide = () => {
  currentSlide.value =
    (currentSlide.value - 1 + testimonials.length) % testimonials.length;
};
</script>
