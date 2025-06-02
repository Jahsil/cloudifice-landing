<template>
  <div
    class="bg-white rounded-xl shadow-md overflow-hidden hover:shadow-xl transition duration-500 transform hover:-translate-y-2"
  >
    <div class="p-6">
      <div class="flex items-center mb-4">
        <div :class="[feature.bgColor, 'p-3 rounded-lg']">
          <svg
            class="w-6 h-6"
            :class="feature.color"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              :d="feature.icon"
            ></path>
          </svg>
        </div>
      </div>
      <h3 class="text-xl font-semibold text-gray-800 mb-2">
        {{ feature.title }}
      </h3>
      <p class="text-gray-600">{{ feature.description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  feature: {
    type: Object,
    required: true,
  },
});
</script>
