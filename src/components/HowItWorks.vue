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

      <!-- Steps Flow -->
      <div class="relative max-w-5xl mx-auto">
        <!-- Connecting Line (Desktop) -->
        <div class="hidden md:block absolute top-[4.5rem] left-[15%] right-[15%] h-[2px] bg-[#2539e6] z-0"></div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 md:gap-8 relative z-10">
          
          <!-- Step 1 -->
          <div class="bg-white rounded-3xl p-8 md:p-10 shadow-sm border border-gray-50 flex flex-col items-center text-center group hover:shadow-md transition-shadow">
            <!-- Icon -->
            <div class="w-16 h-16 bg-[#2539e6] text-white rounded-2xl flex items-center justify-center shadow-lg shadow-blue-500/30 mb-8 transform group-hover:-translate-y-1 transition-transform">
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 0;">person_add</span>
            </div>
            <!-- Label -->
            <div class="text-[#2539e6] text-xs font-black tracking-widest uppercase mb-3">Langkah 1</div>
            <!-- Title -->
            <h3 class="text-xl font-bold text-gray-900 mb-3">Daftar Akun</h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm leading-relaxed">
              Buka CashBaik dan daftar gratis hanya dalam 30 detik. Tidak perlu biaya pendaftaran.
            </p>
          </div>

          <!-- Step 2 -->
          <div class="bg-white rounded-3xl p-8 md:p-10 shadow-sm border border-gray-50 flex flex-col items-center text-center group hover:shadow-md transition-shadow">
            <!-- Icon -->
            <div class="w-16 h-16 bg-[#2539e6] text-white rounded-2xl flex items-center justify-center shadow-lg shadow-blue-500/30 mb-8 transform group-hover:-translate-y-1 transition-transform">
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 0;">local_mall</span>
            </div>
            <!-- Label -->
            <div class="text-[#2539e6] text-xs font-black tracking-widest uppercase mb-3">Langkah 2</div>
            <!-- Title -->
            <h3 class="text-xl font-bold text-gray-900 mb-3">Belanja via Link</h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm leading-relaxed">
              Pilih marketplace favorit kamu dan belanja seperti biasa melalui link CashBaik.
            </p>
          </div>

          <!-- Step 3 -->
          <div class="bg-white rounded-3xl p-8 md:p-10 shadow-sm border border-gray-50 flex flex-col items-center text-center group hover:shadow-md transition-shadow">
            <!-- Icon -->
            <div class="w-16 h-16 bg-[#2539e6] text-white rounded-2xl flex items-center justify-center shadow-lg shadow-blue-500/30 mb-8 transform group-hover:-translate-y-1 transition-transform">
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 0;">payments</span>
            </div>
            <!-- Label -->
            <div class="text-[#2539e6] text-xs font-black tracking-widest uppercase mb-3">Langkah 3</div>
            <!-- Title -->
            <h3 class="text-xl font-bold text-gray-900 mb-3">Cairkan Cashback</h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm leading-relaxed">
              Tarik dana cashback kamu ke rekening bank atau e-wallet. Mendukung banyak metode penarikan.
            </p>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Static component representation
</script>