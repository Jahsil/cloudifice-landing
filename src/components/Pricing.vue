<template>
  <section id="pricing" class="py-20 bg-gray-50">
    <div class="container mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Simple, Transparent Pricing
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Choose the plan that fits your needs. Scale up or down as needed.
        </p>

        <div class="mt-8 flex justify-center">
          <div class="inline-flex items-center bg-gray-200 rounded-full p-1">
            <button
              @click="billingCycle = 'monthly'"
              :class="{
                'bg-white text-indigo-600': billingCycle === 'monthly',
                'text-gray-700': billingCycle !== 'monthly',
              }"
              class="px-6 py-2 rounded-full font-medium focus:outline-none transition"
            >
              Monthly
            </button>
            <button
              @click="billingCycle = 'yearly'"
              :class="{
                'bg-white text-indigo-600': billingCycle === 'yearly',
                'text-gray-700': billingCycle !== 'yearly',
              }"
              class="px-6 py-2 rounded-full font-medium focus:outline-none transition"
            >
              Yearly
              <span
                class="text-sm bg-indigo-100 text-indigo-800 px-2 py-1 rounded-full ml-1"
                >Save 20%</span
              >
            </button>
          </div>
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        <PricingCard
          v-for="(plan, index) in plans"
          :key="index"
          :plan="plan"
          :billing-cycle="billingCycle"
          :featured="index === 1"
        />
      </div>

      <div class="mt-12 text-center">
        <p class="text-gray-600 mb-4">Need custom enterprise solutions?</p>
        <button
          class="px-6 py-3 border-2 border-indigo-600 text-indigo-600 font-semibold rounded-lg hover:bg-indigo-50 transition"
        >
          Contact Sales
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import PricingCard from './PricingCard.vue';

const billingCycle = ref('monthly');

const plans = [
  {
    name: 'Starter',
    description: 'Perfect for individuals and small teams',
    monthlyPrice: 9,
    yearlyPrice: 86,
    features: [
      '100GB Storage',
      'Up to 5 users',
      'Basic file sharing',
      'Email support',
    ],
    cta: 'Get Started',
  },
  {
    name: 'Professional',
    description: 'For growing teams with more needs',
    monthlyPrice: 29,
    yearlyPrice: 278,
    features: [
      '1TB Storage',
      'Up to 20 users',
      'Advanced sharing controls',
      'Priority support',
      'Basic cluster setup',
    ],
    cta: 'Start Free Trial',
    featured: true,
  },
  {
    name: 'Enterprise',
    description: 'For organizations with custom needs',
    monthlyPrice: 99,
    yearlyPrice: 950,
    features: [
      '10TB+ Storage',
      'Unlimited users',
      'Advanced cluster management',
      '24/7 support',
      'Dedicated account manager',
      'Custom configurations',
    ],
    cta: 'Contact Sales',
  },
];
</script>
