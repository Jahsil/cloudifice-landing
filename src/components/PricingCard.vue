<template>
  <div class="relative" :class="{ 'md:-mt-4 md:mb-4': featured }">
    <div
      v-if="featured"
      class="absolute top-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-indigo-600 text-white text-xs font-semibold px-3 py-1 rounded-full"
    >
      Most Popular
    </div>

    <div
      :class="{
        'border-2 border-indigo-500': featured,
        'border border-gray-200': !featured,
      }"
      class="bg-white rounded-xl overflow-hidden"
    >
      <div class="p-8">
        <h3 class="text-2xl font-bold text-gray-800 mb-2">{{ plan.name }}</h3>
        <p class="text-gray-600 mb-6">{{ plan.description }}</p>

        <div class="mb-8">
          <span class="text-4xl font-bold text-gray-900">
            ${{
              billingCycle === 'monthly' ? plan.monthlyPrice : plan.yearlyPrice
            }}
          </span>
          <span class="text-gray-600"
            >/{{ billingCycle === 'monthly' ? 'month' : 'year' }}</span
          >
        </div>

        <button
          :class="{
            'bg-indigo-600 hover:bg-indigo-700 text-white': featured,
            'bg-gray-100 hover:bg-gray-200 text-gray-800': !featured,
          }"
          class="w-full py-3 px-6 rounded-lg font-semibold transition"
        >
          {{ plan.cta }}
        </button>
      </div>

      <div class="border-t border-gray-200 px-8 py-6">
        <h4
          class="text-sm font-semibold text-gray-500 uppercase tracking-wider mb-4"
        >
          Features
        </h4>
        <ul class="space-y-3">
          <li
            v-for="(feature, index) in plan.features"
            :key="index"
            class="flex items-start"
          >
            <svg
              class="w-5 h-5 text-green-500 mr-3 mt-0.5 flex-shrink-0"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M5 13l4 4L19 7"
              ></path>
            </svg>
            <span class="text-gray-700">{{ feature }}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  plan: {
    type: Object,
    required: true,
  },
  billingCycle: {
    type: String,
    required: true,
  },
  featured: {
    type: Boolean,
    default: false,
  },
});
</script>
