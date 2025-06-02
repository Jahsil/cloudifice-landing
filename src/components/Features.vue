<template>
  <section
    id="features"
    class="py-24 bg-gradient-to-br from-gray-900 via-purple-900 to-indigo-900 relative overflow-hidden"
  >
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="feature-bubble feature-bubble-1"></div>
      <div class="feature-bubble feature-bubble-2"></div>
      <div class="feature-bubble feature-bubble-3"></div>
    </div>

    <!-- Subtle Grid Background -->
    <div class="absolute inset-0 opacity-5">
      <div class="grid-background"></div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <!-- Section Header -->
      <div class="text-center mb-20 fade-in-up">
        <div
          class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-sm border border-white/20 mb-6"
        >
          <span class="text-sm text-white/90">✨ Everything you need</span>
        </div>
        <h2 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 text-white">
          <span
            class="bg-gradient-to-r from-indigo-400 via-purple-400 to-cyan-400 bg-clip-text text-transparent"
          >
            Powerful Features
          </span>
        </h2>
        <p
          class="text-xl md:text-2xl text-gray-300 max-w-3xl mx-auto leading-relaxed"
        >
          Modern file storage, sharing, and collaboration tools designed for
          teams that demand excellence
        </p>
      </div>

      <!-- Features Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="(feature, index) in features"
          :key="index"
          class="feature-card fade-in-up"
          :style="{ animationDelay: `${index * 100 + 200}ms` }"
        >
          <!-- Feature Icon -->
          <div class="feature-icon-container mb-6">
            <div :class="feature.bgColor" class="feature-icon-bg">
              <svg
                class="w-8 h-8"
                :class="feature.color"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  :d="feature.icon"
                />
              </svg>
            </div>
          </div>

          <!-- Feature Content -->
          <div>
            <h3
              class="text-xl font-bold text-white mb-4 group-hover:text-transparent group-hover:bg-clip-text group-hover:bg-gradient-to-r group-hover:from-indigo-400 group-hover:to-cyan-400 transition-all duration-300"
            >
              {{ feature.title }}
            </h3>
            <p class="text-gray-300 leading-relaxed">
              {{ feature.description }}
            </p>
          </div>

          <!-- Hover Effect -->
          <div class="feature-card-glow"></div>
        </div>
      </div>

      <!-- Bottom CTA -->
      <div class="text-center mt-20 fade-in-up" style="animation-delay: 800ms">
        <button
          class="px-8 py-4 rounded-xl bg-gradient-to-r from-indigo-600 to-cyan-600 text-white font-semibold text-lg hover:shadow-xl hover:shadow-cyan-500/30 transition-all duration-300 hover:-translate-y-1 hover:scale-105"
        >
          Explore All Features
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
const features = [
  {
    title: 'Distributed Storage',
    description:
      'Store files across multiple nodes with automatic replication and failover for maximum reliability.',
    icon: 'M4 7v10c0 2.21 3.582 4 8 4s8-1.79 8-4V7M4 7c0 2.21 3.582 4 8 4s8-1.79 8-4M4 7c0-2.21 3.582-4 8-4s8 1.79 8 4m0 5c0 2.21-3.582 4-8 4s-8-1.79-8-4',
    color: 'text-indigo-400',
    bgColor: 'bg-gradient-to-br from-indigo-500/20 to-purple-500/20',
  },
  {
    title: 'Advanced Management',
    description:
      'Configure nodes, IPs, chunk sizes, and replication settings with an intuitive interface.',
    icon: 'M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z M15 12a3 3 0 11-6 0 3 3 0 016 0z',
    color: 'text-purple-400',
    bgColor: 'bg-gradient-to-br from-purple-500/20 to-pink-500/20',
  },
  {
    title: 'Real-time Collaboration',
    description:
      'Built-in chat and collaboration tools for seamless teamwork around your files.',
    icon: 'M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z',
    color: 'text-pink-400',
    bgColor: 'bg-gradient-to-br from-pink-500/20 to-rose-500/20',
  },
  {
    title: 'Secure Sharing',
    description:
      'Share files with fine-grained permissions, expiration dates, and access controls.',
    icon: 'M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z',
    color: 'text-blue-400',
    bgColor: 'bg-gradient-to-br from-blue-500/20 to-cyan-500/20',
  },
  {
    title: 'Media Streaming',
    description:
      'Stream videos and audio files directly without downloading, with adaptive quality.',
    icon: 'M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z M21 12a9 9 0 11-18 0 9 9 0 0118 0z',
    color: 'text-green-400',
    bgColor: 'bg-gradient-to-br from-green-500/20 to-emerald-500/20',
  },
  {
    title: 'Self-Hosted Solution',
    description:
      'Deploy on your own infrastructure with full control over your data and privacy.',
    icon: 'M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01',
    color: 'text-orange-400',
    bgColor: 'bg-gradient-to-br from-orange-500/20 to-yellow-500/20',
  },
];
</script>

<style scoped>
/* Background Bubbles */
.feature-bubble {
  position: absolute;
  border-radius: 50%;
  opacity: 0.1;
  pointer-events: none;
}

.feature-bubble-1 {
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  top: 10%;
  right: 10%;
  animation: float1 25s ease-in-out infinite;
}

.feature-bubble-2 {
  width: 150px;
  height: 150px;
  background: linear-gradient(135deg, #8b5cf6, #ec4899);
  bottom: 20%;
  left: 10%;
  animation: float2 30s ease-in-out infinite;
}

.feature-bubble-3 {
  width: 100px;
  height: 100px;
  background: linear-gradient(135deg, #06b6d4, #3b82f6);
  top: 50%;
  left: 50%;
  animation: float3 20s ease-in-out infinite;
}

/* Grid Background */
.grid-background {
  background-image: linear-gradient(
      rgba(255, 255, 255, 0.1) 1px,
      transparent 1px
    ),
    linear-gradient(90deg, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
  background-size: 60px 60px;
  width: 100%;
  height: 100%;
  animation: grid-move 40s linear infinite;
}

/* Feature Card Styles */
.feature-card {
  position: relative;
  padding: 2rem;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1.5rem;
  transition: all 0.5s ease;
  cursor: pointer;
  overflow: hidden;
  group: true;
}

.feature-card:hover {
  transform: translateY(-8px) scale(1.02);
  background: rgba(255, 255, 255, 0.08);
  border-color: rgba(255, 255, 255, 0.2);
}

/* Feature Icon */
.feature-icon-container {
  position: relative;
}

.feature-icon-bg {
  width: 4rem;
  height: 4rem;
  border-radius: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.feature-card:hover .feature-icon-bg {
  transform: scale(1.1) rotate(5deg);
}

/* Feature Card Glow Effect */
.feature-card-glow {
  position: absolute;
  inset: -2px;
  background: linear-gradient(
    135deg,
    rgba(99, 102, 241, 0.2),
    rgba(139, 92, 246, 0.2),
    rgba(6, 182, 212, 0.2)
  );
  border-radius: 1.5rem;
  opacity: 0;
  transition: opacity 0.5s ease;
  z-index: -1;
  filter: blur(20px);
}

.feature-card:hover .feature-card-glow {
  opacity: 1;
}

/* Animations */
@keyframes float1 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  33% {
    transform: translate(-30px, -20px) rotate(120deg);
  }
  66% {
    transform: translate(20px, 30px) rotate(240deg);
  }
}

@keyframes float2 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  50% {
    transform: translate(40px, -30px) rotate(180deg);
  }
}

@keyframes float3 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  25% {
    transform: translate(-20px, 20px) rotate(90deg);
  }
  75% {
    transform: translate(30px, -25px) rotate(270deg);
  }
}

@keyframes grid-move {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(60px, 60px);
  }
}

/* Fade in animations */
.fade-in-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInUp 1s ease-out forwards;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .feature-card {
    padding: 1.5rem;
  }

  .feature-icon-bg {
    width: 3rem;
    height: 3rem;
  }

  .feature-bubble {
    display: none;
  }
}
</style>
