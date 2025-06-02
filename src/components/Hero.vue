<template>
  <section
    class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-gray-900 via-purple-900 to-indigo-900"
  >
    <!-- Simplified Floating Bubbles (No Random Recalculation) -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="bubble bubble-1"></div>
      <div class="bubble bubble-2"></div>
      <div class="bubble bubble-3"></div>
      <div class="bubble bubble-4"></div>
      <div class="bubble bubble-5"></div>
      <div class="bubble bubble-6"></div>
    </div>

    <!-- Subtle Grid Background -->
    <div class="absolute inset-0 opacity-5">
      <div class="grid-background"></div>
    </div>

    <!-- Hero Content -->
    <div class="container mx-auto px-6 relative z-10 text-center">
      <div class="max-w-5xl mx-auto">
        <!-- Simple Badge -->
        <div
          class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-sm border border-white/20 mb-16 fade-in"
        >
          <!-- <div class="w-2 h-2 bg-green-400 rounded-full pulse"></div>
          <span class="text-sm text-white/90"
            >✨ Trusted by 50,000+ companies</span
          > -->
        </div>

        <!-- Main Heading -->
        <h1
          class="text-5xl md:text-7xl lg:text-8xl font-bold mb-8 leading-tight text-white fade-in-up"
        >
          <span
            class="bg-gradient-to-r from-indigo-400 via-purple-400 to-cyan-400 bg-clip-text text-transparent"
          >
            Cloud Storage
          </span>
          <br />
          <span class="text-white">Made Simple</span>
        </h1>

        <!-- Subtitle -->
        <p
          class="text-xl md:text-2xl text-gray-300 mb-12 max-w-3xl mx-auto leading-relaxed fade-in-up delay-200"
        >
          Store, share, and collaborate on your files with enterprise-grade
          security and lightning-fast performance.
        </p>

        <!-- CTA Buttons -->
        <div
          class="flex flex-col sm:flex-row justify-center gap-6 mb-16 fade-in-up delay-400"
        >
          <button class="cta-primary">Start Free Trial</button>
          <button class="cta-secondary">
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
                d="M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z"
              ></path>
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
              ></path>
            </svg>
            <span>Watch Demo</span>
          </button>
        </div>

        <!-- Clean Dashboard Preview -->
        <div class="relative group fade-in-up delay-600">
          <div class="relative max-w-4xl mx-auto">
            <!-- Glow Effect -->
            <div
              class="absolute -inset-4 bg-gradient-to-r from-indigo-500/20 to-cyan-500/20 rounded-2xl blur-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700"
            ></div>

            <!-- Dashboard Container -->
            <div
              class="relative bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl p-6 shadow-2xl hover:transform hover:scale-105 transition-all duration-500"
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
                  dashboard.cloudifice.et
                </div>
              </div>

              <!-- Dashboard Stats -->
              <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
                <div
                  class="bg-gradient-to-br from-indigo-500/10 to-purple-500/10 rounded-xl p-4 border border-white/5"
                >
                  <div class="text-white/60 text-sm mb-1">Storage Used</div>
                  <div class="text-2xl font-bold text-white">2.4 TB</div>
                  <div class="w-full bg-white/10 rounded-full h-1.5 mt-2">
                    <div
                      class="bg-gradient-to-r from-indigo-500 to-cyan-500 h-1.5 rounded-full progress-bar"
                    ></div>
                  </div>
                </div>

                <div
                  class="bg-gradient-to-br from-purple-500/10 to-pink-500/10 rounded-xl p-4 border border-white/5"
                >
                  <div class="text-white/60 text-sm mb-1">Files</div>
                  <div class="text-2xl font-bold text-white">15,847</div>
                  <div class="text-green-400 text-sm mt-1">
                    ↗ +12% this month
                  </div>
                </div>

                <div
                  class="bg-gradient-to-br from-cyan-500/10 to-blue-500/10 rounded-xl p-4 border border-white/5"
                >
                  <div class="text-white/60 text-sm mb-1">Team Members</div>
                  <div class="text-2xl font-bold text-white">24</div>
                  <div class="flex -space-x-1 mt-2">
                    <div
                      class="w-6 h-6 rounded-full bg-gradient-to-br from-indigo-500 to-purple-500 border border-white/20"
                    ></div>
                    <div
                      class="w-6 h-6 rounded-full bg-gradient-to-br from-cyan-500 to-blue-500 border border-white/20"
                    ></div>
                    <div
                      class="w-6 h-6 rounded-full bg-gradient-to-br from-purple-500 to-pink-500 border border-white/20"
                    ></div>
                  </div>
                </div>
              </div>

              <!-- Recent Files -->
              <div class="space-y-2">
                <div class="text-white/60 text-sm mb-3">Recent Files</div>
                <div class="file-item">
                  <div
                    class="w-8 h-8 rounded-lg bg-gradient-to-br from-blue-500 to-indigo-500 flex items-center justify-center text-white text-xs font-bold"
                  >
                    PDF
                  </div>
                  <div class="flex-1">
                    <div class="text-white font-medium">
                      Project Proposal.pdf
                    </div>
                    <div class="text-white/50 text-sm">
                      2.4 MB • 2 hours ago
                    </div>
                  </div>
                  <div class="w-2 h-2 bg-green-400 rounded-full pulse"></div>
                </div>

                <div class="file-item">
                  <div
                    class="w-8 h-8 rounded-lg bg-gradient-to-br from-green-500 to-emerald-500 flex items-center justify-center text-white text-xs font-bold"
                  >
                    XLS
                  </div>
                  <div class="flex-1">
                    <div class="text-white font-medium">Q4 Reports.xlsx</div>
                    <div class="text-white/50 text-sm">890 KB • 1 day ago</div>
                  </div>
                  <div class="w-2 h-2 bg-blue-400 rounded-full pulse"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Simplified Bubble Animations (Fixed Positions) */
.bubble {
  position: absolute;
  border-radius: 50%;
  opacity: 0.1;
  pointer-events: none;
}

.bubble-1 {
  width: 120px;
  height: 120px;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  top: 10%;
  left: 10%;
  animation: float1 20s ease-in-out infinite;
}

.bubble-2 {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #8b5cf6, #ec4899);
  top: 20%;
  right: 15%;
  animation: float2 25s ease-in-out infinite;
}

.bubble-3 {
  width: 100px;
  height: 100px;
  background: linear-gradient(135deg, #06b6d4, #3b82f6);
  bottom: 20%;
  left: 20%;
  animation: float3 30s ease-in-out infinite;
}

.bubble-4 {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #6366f1, #06b6d4);
  top: 60%;
  right: 25%;
  animation: float4 22s ease-in-out infinite;
}

.bubble-5 {
  width: 140px;
  height: 140px;
  background: linear-gradient(135deg, #8b5cf6, #6366f1);
  bottom: 10%;
  right: 10%;
  animation: float5 28s ease-in-out infinite;
}

.bubble-6 {
  width: 90px;
  height: 90px;
  background: linear-gradient(135deg, #ec4899, #8b5cf6);
  top: 40%;
  left: 5%;
  animation: float6 24s ease-in-out infinite;
}

/* Unique float animations for each bubble */
@keyframes float1 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  33% {
    transform: translate(30px, -30px) rotate(120deg);
  }
  66% {
    transform: translate(-20px, 20px) rotate(240deg);
  }
}

@keyframes float2 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  50% {
    transform: translate(-40px, 30px) rotate(180deg);
  }
}

@keyframes float3 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  25% {
    transform: translate(20px, -40px) rotate(90deg);
  }
  75% {
    transform: translate(-30px, -20px) rotate(270deg);
  }
}

@keyframes float4 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  50% {
    transform: translate(25px, 25px) rotate(180deg);
  }
}

@keyframes float5 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  40% {
    transform: translate(-25px, -35px) rotate(144deg);
  }
  80% {
    transform: translate(35px, 15px) rotate(288deg);
  }
}

@keyframes float6 {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  60% {
    transform: translate(15px, -25px) rotate(216deg);
  }
}

/* Grid Background */
.grid-background {
  background-image: linear-gradient(
      rgba(255, 255, 255, 0.1) 1px,
      transparent 1px
    ),
    linear-gradient(90deg, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
  background-size: 50px 50px;
  width: 100%;
  height: 100%;
  animation: grid-move 30s linear infinite;
}

@keyframes grid-move {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(50px, 50px);
  }
}

/* Fade in animations */
.fade-in {
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}

.fade-in-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInUp 1s ease-out forwards;
}

.delay-200 {
  animation-delay: 0.2s;
}
.delay-400 {
  animation-delay: 0.4s;
}
.delay-600 {
  animation-delay: 0.6s;
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Button Styles */
.cta-primary {
  @apply px-8 py-4 rounded-xl bg-gradient-to-r from-indigo-600 to-cyan-600 text-white font-semibold text-lg transition-all duration-300 hover:shadow-xl hover:shadow-cyan-500/30 hover:-translate-y-1 hover:scale-105;
}

.cta-secondary {
  @apply px-8 py-4 rounded-xl border-2 border-white/30 text-white font-semibold text-lg hover:border-cyan-400 hover:text-cyan-400 hover:bg-white/5 transition-all duration-300 flex items-center justify-center gap-3 hover:scale-105;
}

/* File item styles */
.file-item {
  @apply flex items-center gap-3 p-3 bg-white/5 rounded-lg border border-white/5 hover:bg-white/10 transition-all duration-300;
}

/* Progress bar animation */
.progress-bar {
  width: 0;
  animation: progressGrow 2s ease-out 1s forwards;
}

@keyframes progressGrow {
  to {
    width: 75%;
  }
}

/* Pulse animation */
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
</style>
