<template>
  <section class="py-24 relative overflow-hidden" id="cara-kerja">
    <!-- Dotted Background -->
    <div class="absolute inset-0 -z-20 bg-[#f8faff]"></div>
    <div class="absolute inset-0 -z-10" style="background-image: radial-gradient(#d1d5db 1px, transparent 1px); background-size: 24px 24px;"></div>

    <div class="max-w-7xl mx-auto px-6 md:px-12 relative">
      <!-- Section Header -->
      <div class="text-center max-w-2xl mx-auto mb-16">
        <div class="inline-block bg-[#eef0ff] text-[#2539e6] text-xs font-bold px-4 py-1.5 rounded-full mb-6">
          Mudah & Cepat
        </div>
        <h2 class="text-3xl md:text-4xl font-extrabold text-gray-900 mb-4 tracking-tight">Cara Kerja CashBaik</h2>
        <p class="text-gray-500 text-lg">
          Hanya 3 langkah mudah untuk mulai mendapatkan cashback dari belanja online.
        </p>
      </div>

      <!-- Steps Flow (Hover Effect) -->
      <div class="relative max-w-5xl mx-auto">
        <!-- Connecting Line Background (Desktop) -->
        <div class="hidden md:block absolute top-[4.5rem] left-[15%] right-[15%] h-[2px] bg-[#2539e6]/20 z-0"></div>
        <!-- Connecting Line Hover Highlight (Desktop) -->
        <div
          class="hidden md:block absolute top-[4.5rem] left-[15%] h-[2px] bg-[#2539e6] z-0 transition-all duration-500 ease-in-out"
          :style="{ width: hoveredStep ? `${(hoveredStep - 1) * 35}%` : '0%' }"
        ></div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-8 relative z-10">

          <div
            v-for="(step, index) in steps"
            :key="step.id"
            @mouseenter="hoveredStep = step.id"
            @mouseleave="hoveredStep = null"
            :class="[
              'rounded-3xl p-8 md:p-10 border bg-white flex flex-col items-center text-center cursor-default transition-all duration-300',
              hoveredStep === step.id
                ? 'border-[#2539e6] shadow-xl shadow-blue-500/10 -translate-y-2 scale-105 ring-2 ring-[#2539e6]/20'
                : 'border-gray-100 shadow-sm'
            ]"
          >
            <!-- Icon — always blue -->
            <div class="w-16 h-16 bg-[#2539e6] text-white rounded-2xl flex items-center justify-center shadow-lg shadow-blue-500/30 mb-8 transition-transform duration-300"
              :class="hoveredStep === step.id ? 'scale-110' : 'scale-100'"
            >
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 0;">
                {{ step.icon }}
              </span>
            </div>
            <!-- Label — always blue -->
            <div class="text-[#2539e6] text-xs font-black tracking-widest uppercase mb-3">
              Langkah {{ index + 1 }}
            </div>
            <!-- Title -->
            <h3 class="text-xl font-bold text-gray-900 mb-3">
              {{ step.title }}
            </h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm leading-relaxed">
              {{ step.description }}
            </p>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const hoveredStep = ref(null)

const steps = [
  {
    id: 1,
    icon: 'person_add',
    title: 'Daftar Akun',
    description: 'Buka CashBaik dan daftar gratis hanya dalam 30 detik. Tidak perlu biaya pendaftaran.'
  },
  {
    id: 2,
    icon: 'local_mall',
    title: 'Belanja via Link',
    description: 'Pilih marketplace favorit kamu dan belanja seperti biasa melalui link CashBaik.'
  },
  {
    id: 3,
    icon: 'payments',
    title: 'Cairkan Cashback',
    description: 'Tarik dana cashback kamu ke rekening bank atau e-wallet. Mendukung banyak metode penarikan.'
  }
]
</script>