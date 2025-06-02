<template>
  <section
    id="demo"
    class="py-24 bg-gradient-to-br from-gray-900 via-purple-900 to-indigo-900 relative overflow-hidden"
  >
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="demo-bubble demo-bubble-1"></div>
      <div class="demo-bubble demo-bubble-2"></div>
      <div class="demo-bubble demo-bubble-3"></div>
    </div>

    <!-- Subtle Grid Background -->
    <div class="absolute inset-0 opacity-5">
      <div class="grid-background"></div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <div class="flex flex-col lg:flex-row items-center gap-16">
        <!-- Content Section -->
        <div class="lg:w-1/2 text-white fade-in-up">
          <!-- Section Badge -->
          <div
            class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-sm border border-white/20 mb-6"
          >
            <div class="w-2 h-2 bg-cyan-400 rounded-full pulse"></div>
            <span class="text-sm text-white/90">✨ See it in action</span>
          </div>

          <h2
            class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 leading-tight"
          >
            <span
              class="bg-gradient-to-r from-indigo-400 via-purple-400 to-cyan-400 bg-clip-text text-transparent"
            >
              Experience Cloudifice
            </span>
            <br />
            <span class="text-white">In Real-Time</span>
          </h2>

          <p class="text-xl md:text-2xl text-gray-300 mb-8 leading-relaxed">
            Watch our interactive demo to see how Cloudifice transforms your
            file storage and collaboration workflows in just minutes.
          </p>

          <!-- Feature List -->
          <div class="space-y-4 mb-8">
            <div
              v-for="(feature, index) in demoFeatures"
              :key="index"
              class="flex items-start gap-4 feature-item fade-in-up"
              :style="{ animationDelay: `${index * 150 + 300}ms` }"
            >
              <div class="feature-check">
                <svg
                  class="w-5 h-5 text-white"
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
              </div>
              <span class="text-gray-300 leading-relaxed">{{ feature }}</span>
            </div>
          </div>

          <!-- Video Controls -->
          <div
            class="flex items-center gap-4 mb-8 fade-in-up"
            style="animation-delay: 700ms"
          >
            <button
              @click="toggleVideo"
              class="flex items-center gap-2 px-4 py-2 bg-white/10 hover:bg-white/20 rounded-lg transition-colors duration-300"
            >
              <svg
                v-if="isPlaying"
                class="w-5 h-5 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M10 9v6m4-6v6"
                ></path>
              </svg>
              <svg
                v-else
                class="w-5 h-5 text-white"
                fill="currentColor"
                viewBox="0 0 24 24"
              >
                <path d="M8 5v14l11-7z" />
              </svg>
              <span class="text-white text-sm">{{
                isPlaying ? 'Pause' : 'Play'
              }}</span>
            </button>

            <button
              @click="toggleMute"
              class="flex items-center gap-2 px-4 py-2 bg-white/10 hover:bg-white/20 rounded-lg transition-colors duration-300"
            >
              <svg
                v-if="isMuted"
                class="w-5 h-5 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z"
                  clip-rule="evenodd"
                ></path>
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M17 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2"
                ></path>
              </svg>
              <svg
                v-else
                class="w-5 h-5 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z"
                ></path>
              </svg>
              <span class="text-white text-sm">{{
                isMuted ? 'Unmute' : 'Mute'
              }}</span>
            </button>

            <button
              @click="openFullscreen"
              class="flex items-center gap-2 px-4 py-2 bg-white/10 hover:bg-white/20 rounded-lg transition-colors duration-300"
            >
              <svg
                class="w-5 h-5 text-white"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 8V4m0 0h4M4 4l5 5m11-1V4m0 0h-4m4 0l-5 5M4 16v4m0 0h4m-4 0l5-5m11 5l-5-5m5 5v-4m0 4h-4"
                ></path>
              </svg>
              <span class="text-white text-sm">Fullscreen</span>
            </button>
          </div>

          <!-- CTA Buttons -->
          <div
            class="flex flex-col sm:flex-row gap-4 fade-in-up"
            style="animation-delay: 900ms"
          >
            <button class="demo-cta-primary">Try Interactive Demo</button>
            <button class="demo-cta-secondary">
              <svg
                class="w-5 h-5"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"
                ></path>
              </svg>
              <span>Download Demo Guide</span>
            </button>
          </div>
        </div>

        <!-- Video Section -->
        <div
          class="lg:w-1/2 relative fade-in-up"
          style="animation-delay: 600ms"
        >
          <div class="relative video-container group">
            <!-- Glow Effect -->
            <div
              class="absolute -inset-4 bg-gradient-to-r from-indigo-500/30 to-cyan-500/30 rounded-3xl blur-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700"
            ></div>

            <!-- Video Container -->
            <div
              class="relative bg-white/5 backdrop-blur-xl border border-white/10 rounded-3xl p-6 shadow-2xl"
            >
              <!-- Browser Header -->
              <div
                class="flex items-center justify-between mb-4 pb-4 border-b border-white/10"
              >
                <div class="flex items-center gap-2">
                  <div class="w-3 h-3 bg-red-500 rounded-full"></div>
                  <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
                  <div class="w-3 h-3 bg-green-500 rounded-full"></div>
                </div>
                <div class="text-white/40 text-sm font-mono">
                  demo.cloudifice.et
                </div>
              </div>

              <!-- Auto-playing Video -->
              <div class="relative rounded-2xl overflow-hidden">
                <div
                  ref="videoContainer"
                  class="aspect-video bg-gradient-to-br from-gray-800 to-gray-900"
                >
                  <!-- YouTube Video Embed with Autoplay -->
                  <iframe
                    ref="videoIframe"
                    :src="videoUrl"
                    class="w-full h-full rounded-2xl"
                    frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                    allowfullscreen
                    @load="onVideoLoad"
                  ></iframe>
                </div>

                <!-- Video Stats Overlay -->
                <div class="video-stats">
                  <div class="flex items-center gap-2 text-white text-sm">
                    <svg
                      class="w-4 h-4"
                      fill="none"
                      stroke="currentColor"
                      viewBox="0 0 24 24"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
                      ></path>
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"
                      ></path>
                    </svg>
                    <span class="live-indicator pulse"></span>
                    LIVE DEMO
                  </div>
                  <div class="text-white text-sm">HD 1080p</div>
                </div>
              </div>
            </div>
          </div>

          <!-- Demo Stats -->
          <div class="grid grid-cols-3 gap-4 mt-8">
            <div
              class="text-center p-4 bg-white/5 backdrop-blur-sm rounded-xl border border-white/10"
            >
              <div class="text-2xl font-bold text-white mb-1">
                {{ formatNumber(demoViews) }}+
              </div>
              <div class="text-white/60 text-sm">Demo Views</div>
            </div>
            <div
              class="text-center p-4 bg-white/5 backdrop-blur-sm rounded-xl border border-white/10"
            >
              <div class="text-2xl font-bold text-white mb-1">
                {{ formatNumber(trialsStarted) }}
              </div>
              <div class="text-white/60 text-sm">Trials Started</div>
            </div>
            <div
              class="text-center p-4 bg-white/5 backdrop-blur-sm rounded-xl border border-white/10"
            >
              <div class="text-2xl font-bold text-white mb-1">4.9★</div>
              <div class="text-white/60 text-sm">User Rating</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Fullscreen Video Modal -->
    <div
      v-if="showFullscreen"
      class="fixed inset-0 bg-black z-50 flex items-center justify-center"
      @click="closeFullscreen"
    >
      <div class="relative w-full h-full" @click.stop>
        <button
          @click="closeFullscreen"
          class="absolute top-4 right-4 z-10 w-12 h-12 bg-black/50 hover:bg-black/70 rounded-full flex items-center justify-center text-white transition-colors duration-300"
        >
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            ></path>
          </svg>
        </button>

        <iframe
          :src="fullscreenVideoUrl"
          class="w-full h-full"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue';

const videoContainer = ref(null);
const videoIframe = ref(null);
const showFullscreen = ref(false);
const isPlaying = ref(true);
const isMuted = ref(true); // Start muted to comply with browser autoplay policies
const videoLoaded = ref(false);
const demoViews = ref(50000);
const trialsStarted = ref(3200);

// YouTube video ID - replace with your actual cloud storage demo video
const VIDEO_ID = 'dQw4w9WgXcQ'; // Replace with your actual video ID

const demoFeatures = [
  'Set up distributed storage clusters in under 5 minutes',
  'Real-time collaboration with built-in team chat',
  'Advanced file sharing with granular permissions',
  'Military-grade encryption for maximum security',
];

const videoUrl = computed(() => {
  const params = new URLSearchParams({
    autoplay: '1',
    mute: isMuted.value ? '1' : '0',
    controls: '0', // Hide controls for cleaner look
    modestbranding: '1',
    rel: '0',
    showinfo: '0',
    loop: '1',
    playlist: VIDEO_ID, // Required for loop to work
    enablejsapi: '1', // Enable JavaScript API
  });
  return `https://www.youtube.com/embed/${VIDEO_ID}?${params.toString()}`;
});

const fullscreenVideoUrl = computed(() => {
  const params = new URLSearchParams({
    autoplay: '1',
    controls: '1',
    modestbranding: '1',
    rel: '0',
  });
  return `https://www.youtube.com/embed/${VIDEO_ID}?${params.toString()}`;
});

const formatNumber = (num) => {
  if (num >= 1000) {
    return (num / 1000).toFixed(1) + 'K';
  }
  return num.toString();
};

const toggleVideo = () => {
  // Note: Direct control of YouTube iframe requires YouTube API
  // For now, we'll just toggle the visual state
  isPlaying.value = !isPlaying.value;

  // You can implement YouTube API integration here for actual control
  console.log(isPlaying.value ? 'Playing video' : 'Pausing video');
};

const toggleMute = () => {
  isMuted.value = !isMuted.value;
  // Update the iframe src to change mute state
  const iframe = videoIframe.value;
  if (iframe) {
    iframe.src = videoUrl.value;
  }
};

const openFullscreen = () => {
  showFullscreen.value = true;
  document.body.style.overflow = 'hidden';
};

const closeFullscreen = () => {
  showFullscreen.value = false;
  document.body.style.overflow = 'auto';
};

const onVideoLoad = () => {
  videoLoaded.value = true;
  // Increment view count for demo purposes
  setTimeout(() => {
    demoViews.value += Math.floor(Math.random() * 10) + 1;
  }, 2000);
};

// Intersection Observer to trigger autoplay when section is visible
const observeVideoSection = () => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && !videoLoaded.value) {
          // Video will autoplay when container comes into view
          console.log('Video section is visible, autoplay should start');
        }
      });
    },
    { threshold: 0.5 },
  );

  if (videoContainer.value) {
    observer.observe(videoContainer.value);
  }

  return observer;
};

onMounted(() => {
  const observer = observeVideoSection();

  onUnmounted(() => {
    observer.disconnect();
    document.body.style.overflow = 'auto';
  });
});
</script>

<style scoped>
/* Previous styles remain the same... */
.demo-bubble {
  position: absolute;
  border-radius: 50%;
  opacity: 0.08;
  pointer-events: none;
}

.demo-bubble-1 {
  width: 180px;
  height: 180px;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  top: 15%;
  left: 10%;
  animation: float1 28s ease-in-out infinite;
}

.demo-bubble-2 {
  width: 120px;
  height: 120px;
  background: linear-gradient(135deg, #8b5cf6, #ec4899);
  bottom: 25%;
  right: 15%;
  animation: float2 32s ease-in-out infinite;
}

.demo-bubble-3 {
  width: 90px;
  height: 90px;
  background: linear-gradient(135deg, #06b6d4, #3b82f6);
  top: 60%;
  right: 30%;
  animation: float3 25s ease-in-out infinite;
}

.grid-background {
  background-image: linear-gradient(
      rgba(255, 255, 255, 0.1) 1px,
      transparent 1px
    ),
    linear-gradient(90deg, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
  background-size: 70px 70px;
  width: 100%;
  height: 100%;
  animation: grid-move 45s linear infinite;
}

.feature-check {
  width: 2rem;
  height: 2rem;
  border-radius: 50%;
  background: linear-gradient(135deg, #10b981, #059669);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  animation: check-pulse 2s ease-in-out infinite;
}

.feature-item {
  opacity: 0;
  transform: translateX(-20px);
  animation: slideInLeft 0.6s ease-out forwards;
}

.video-container {
  position: relative;
}

.video-stats {
  position: absolute;
  bottom: 1rem;
  left: 1rem;
  right: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(0, 0, 0, 0.7);
  backdrop-filter: blur(8px);
  border-radius: 0.5rem;
  padding: 0.75rem;
  transition: opacity 0.3s ease;
}

.live-indicator {
  width: 8px;
  height: 8px;
  background: #ef4444;
  border-radius: 50%;
  margin-right: 4px;
}

/* Button Styles */
.demo-cta-primary {
  padding: 1rem 2rem;
  border-radius: 0.75rem;
  background: linear-gradient(to right, #4f46e5, #06b6d4);
  color: white;
  font-weight: 600;
  font-size: 1.125rem;
  transition: all 0.3s ease;
}

.demo-cta-primary:hover {
  transform: translateY(-0.25rem) scale(1.05);
  box-shadow: 0 25px 50px -12px rgba(6, 182, 212, 0.3);
}

.demo-cta-secondary {
  padding: 1rem 2rem;
  border-radius: 0.75rem;
  border: 2px solid rgba(255, 255, 255, 0.3);
  color: white;
  font-weight: 600;
  font-size: 1.125rem;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.75rem;
}

.demo-cta-secondary:hover {
  border-color: #22d3ee;
  color: #22d3ee;
  background: rgba(255, 255, 255, 0.05);
  transform: scale(1.05);
}

/* Animations */
@keyframes float1 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  33% {
    transform: translate(-25px, -30px) rotate(120deg);
  }
  66% {
    transform: translate(30px, 20px) rotate(240deg);
  }
}

@keyframes float2 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  50% {
    transform: translate(35px, -25px) rotate(180deg);
  }
}

@keyframes float3 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  25% {
    transform: translate(-20px, 25px) rotate(90deg);
  }
  75% {
    transform: translate(25px, -20px) rotate(270deg);
  }
}

@keyframes grid-move {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(70px, 70px);
  }
}

@keyframes check-pulse {
  0%,
  100% {
    transform: scale(1);
    box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.4);
  }
  50% {
    transform: scale(1.05);
    box-shadow: 0 0 0 10px rgba(16, 185, 129, 0);
  }
}

@keyframes slideInLeft {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

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

.pulse {
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

@media (max-width: 1024px) {
  .demo-bubble {
    display: none;
  }
}
</style>
