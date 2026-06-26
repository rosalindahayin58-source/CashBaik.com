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
          <div class="w-16 h-16 bg-gray-50 rounded-xl mb-4 flex items-center justify-center p-3 border border-gray-50">
            <component :is="merchant.logoComponent" class="w-full h-full object-contain" />
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
import { h } from 'vue'

// Custom minimalist SVG icons for merchants
const ShopeeLogo = {
  render() {
    return h('svg', { viewBox: '0 0 24 24', fill: 'none', xmlns: 'http://www.w3.org/2000/svg' }, [
      h('path', { d: 'M19 8h-2.5a4.5 4.5 0 00-9 0H5a2 2 0 00-2 2v10a2 2 0 002 2h14a2 2 0 002-2V10a2 2 0 00-2-2zM12 5.5c1.38 0 2.5 1.12 2.5 2.5h-5c0-1.38 1.12-2.5 2.5-2.5z', fill: '#ee4d2d' }),
      h('path', { d: 'M13.5 14.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0z', fill: '#fff' })
    ])
  }
}

const GrabFoodLogo = {
  render() {
    return h('svg', { viewBox: '0 0 24 24', fill: 'none', xmlns: 'http://www.w3.org/2000/svg' }, [
      h('rect', { width: '24', height: '24', rx: '12', fill: '#00b14f' }),
      h('path', { d: 'M7 12a5 5 0 019.5-2.2M17 12a5 5 0 01-9.5 2.2', stroke: '#fff', strokeWidth: '2.5', strokeLinecap: 'round' })
    ])
  }
}

const TokopediaLogo = {
  render() {
    return h('svg', { viewBox: '0 0 24 24', fill: 'none', xmlns: 'http://www.w3.org/2000/svg' }, [
      h('path', { d: 'M4 8.5L12 4l8 4.5V16l-8 4.5-8-4.5V8.5z', fill: '#42b549' }),
      h('circle', { cx: '9.5', cy: '11.5', r: '2.5', fill: '#fff' }),
      h('circle', { cx: '14.5', cy: '11.5', r: '2.5', fill: '#fff' }),
      h('circle', { cx: '9.5', cy: '11.5', r: '1', fill: '#42b549' }),
      h('circle', { cx: '14.5', cy: '11.5', r: '1', fill: '#42b549' })
    ])
  }
}

const TravelokaLogo = {
  render() {
    return h('svg', { viewBox: '0 0 24 24', fill: 'none', xmlns: 'http://www.w3.org/2000/svg' }, [
      h('path', { d: 'M3 13.5c3-1 7.5-6.5 10-8.5s4-1 6-.5-2.5 3-4.5 4.5S8.5 12 7.5 14s-2.5.5-4.5-.5z', fill: '#0194f3' }),
      h('path', { d: 'M13.5 11l6.5 6.5s-2 1-4.5 0-3-4-2-6.5z', fill: '#1ba0e2' })
    ])
  }
}

const TixIdLogo = {
  render() {
    return h('svg', { viewBox: '0 0 24 24', fill: 'none', xmlns: 'http://www.w3.org/2000/svg' }, [
      h('rect', { width: '24', height: '24', rx: '6', fill: '#0c1b33' }),
      h('path', { d: 'M6 8h12v2H6V8zm0 4h12v2H6v-2zm0 4h8v2H6v-2z', fill: '#00d2c4' })
    ])
  }
}

const popularMerchants = [
  {
    name: 'Shopee',
    logoComponent: ShopeeLogo,
    cashback: 'Up to 15% Cashback',
  },
  {
    name: 'GrabFood',
    logoComponent: GrabFoodLogo,
    cashback: 'Rp 1.000 Flat',
  },
  {
    name: 'Tokopedia',
    logoComponent: TokopediaLogo,
    cashback: 'Up to 8% Cashback',
  },
  {
    name: 'Traveloka',
    logoComponent: TravelokaLogo,
    cashback: 'Diskon s/d Rp 500rb',
  },
  {
    name: 'TIX ID',
    logoComponent: TixIdLogo,
    cashback: 'Cashback Rp 5.000',
  },
]
</script>