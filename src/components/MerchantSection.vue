<template>
  <section class="py-20 bg-[#f8fafc]" id="merchant">
    <div class="max-w-7xl mx-auto px-6 md:px-12">
      <!-- Section Header -->
      <div class="flex flex-col md:flex-row justify-between items-start md:items-end mb-12">
        <div>
          <h2 class="text-3xl font-bold text-[#0b1b66] mb-2">Merchant Populer</h2>
          <p class="text-gray-500 font-medium">Belanja di merchant favoritmu dan dapatkan cashback otomatis langsung masuk ke saldo CashBaik-mu.</p>
        </div>
        <a 
          href="#" 
          class="text-[#0b1b66] hover:text-blue-800 font-semibold text-sm flex items-center gap-1 mt-4 md:mt-0 transition-colors"
        >
          Lihat Semua Merchant
          <span class="material-symbols-outlined text-sm font-bold">arrow_forward</span>
        </a>
      </div>

      <!-- Merchant Grid -->
      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5 gap-6">
        <div 
          v-for="merchant in popularMerchants" 
          :key="merchant.name"
          class="bg-white rounded-2xl p-6 border border-gray-100/80 shadow-sm hover:shadow-md hover:-translate-y-1 transition-all duration-300 flex flex-col items-center text-center group cursor-pointer"
        >
          <!-- Logo Container -->
          <div class="w-16 h-16 rounded-xl mb-4 flex items-center justify-center overflow-hidden">
            <img 
              :src="merchant.logo" 
              :alt="merchant.name + ' logo'" 
              class="w-full h-full object-contain"
            />
          </div>
          <!-- Name -->
          <h3 class="font-bold text-gray-800 text-sm mb-2 group-hover:text-[#0b1b66] transition-colors">
            {{ merchant.name }}
          </h3>
          <!-- Badge -->
          <span class="inline-block px-3 py-1 rounded-full bg-[#f0fdf4] text-[#16a34a] font-bold text-xs">
            {{ merchant.cashback }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const popularMerchants = [
  {
    name: 'Shopee',
    logo: '/images/merchant-shopee.png',
    cashback: 'Up to 15% Cashback',
  },
  {
    name: 'GrabFood',
    logo: '/images/merchant-grabfood.png',
    cashback: 'Rp 1.000 Flat',
  },
  {
    name: 'Tokopedia',
    logo: '/images/merchant-tokopedia.png',
    cashback: 'Up to 8% Cashback',
  },
  {
    name: 'Traveloka',
    logo: '/images/merchant-traveloka.png',
    cashback: 'Diskon s/d Rp 500rb',
  },
  {
    name: 'TikTok',
    logo: '/images/merchant-tiktok.png',
    cashback: 'Cashback Rp 5.000',
  },
]
</script>