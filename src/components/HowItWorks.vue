<template>
  <section class="py-24 bg-white" id="cara-kerja">
    <div class="max-w-7xl mx-auto px-6 md:px-12">
      <!-- Section Header -->
      <div class="text-center max-w-2xl mx-auto mb-20">
        <h2 class="text-4xl font-extrabold text-[#0b1b66]">Cara Kerja CashBaik</h2>
        <p>Hanya 3 langkah mudah untuk mulai mendapatkan cashback dari belanja online.
        </p>
      </div>

      <!-- Steps Flow -->
      <div class="relative max-w-5xl mx-auto">
        <!-- Connecting Line (Desktop) -->
        <div class="hidden md:block absolute top-10 left-[15%] right-[15%] h-0.5 bg-gray-200 -z-0"></div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-12 relative z-10">
          <!-- Step 1 -->
          <div class="flex flex-col items-center text-center group">
            <!-- Icon -->
            <div class="w-20 h-20 bg-[#0b1b66] text-white rounded-full flex items-center justify-center shadow-lg transition-transform duration-300 group-hover:scale-110 mb-6">
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 1;">storefront</span>
            </div>
            <!-- Title -->
            <h3 class="text-lg font-bold text-gray-800 mb-2">Pilih Merchant</h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm max-w-xs leading-relaxed">
              Temukan toko favoritmu lewat aplikasi atau website CashBaik.
            </p>
          </div>

          <!-- Step 2 -->
          <div class="flex flex-col items-center text-center group">
            <!-- Icon -->
            <div class="w-20 h-20 bg-[#ffd54a] text-[#0b1b66] rounded-full flex items-center justify-center shadow-lg transition-transform duration-300 group-hover:scale-110 mb-6">
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 1;">shopping_cart</span>
            </div>
            <!-- Title -->
            <h3 class="text-lg font-bold text-gray-800 mb-2">Belanja Biasa</h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm max-w-xs leading-relaxed">
              Lakukan pembelian seperti biasa di situs merchant tersebut.
            </p>
          </div>

          <!-- Step 3 -->
          <div class="flex flex-col items-center text-center group">
            <!-- Icon -->
            <div class="w-20 h-20 bg-[#005d2e] text-white rounded-full flex items-center justify-center shadow-lg transition-transform duration-300 group-hover:scale-110 mb-6">
              <span class="material-symbols-outlined text-3xl" style="font-variation-settings: 'FILL' 1;">payments</span>
            </div>
            <!-- Title -->
            <h3 class="text-lg font-bold text-gray-800 mb-2">Duit Balik!</h3>
            <!-- Description -->
            <p class="text-gray-500 text-sm max-w-xs leading-relaxed">
              Cashback akan masuk ke saldo CashBaik-mu secara otomatis.
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