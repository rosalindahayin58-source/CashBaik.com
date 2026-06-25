<template>
  <header class="fixed top-0 w-full z-50 bg-white border-b border-gray-100">
    <nav class="flex justify-between items-center px-6 md:px-12 py-4 max-w-7xl mx-auto">
      <!-- Logo -->
      <div class="flex items-center gap-2">
        <span class="font-bold text-2xl text-[#000666] tracking-tight">CashBaik</span>
      </div>

      <!-- Navigation Links -->
      <div class="hidden md:flex items-center gap-8">
        <a 
          href="#home" 
          class="text-[#000666] font-semibold text-sm relative py-1 border-b-2 border-[#000666]"
        >
          Home
        </a>
        <a 
          href="#merchant" 
          class="text-gray-500 hover:text-[#000666] font-medium text-sm transition-colors py-1"
        >
          Merchant
        </a>
        <a 
          href="#promo" 
          class="text-gray-500 hover:text-[#000666] font-medium text-sm transition-colors py-1"
        >
          Promo
        </a>
        <a 
          href="#bantuan" 
          class="text-gray-500 hover:text-[#000666] font-medium text-sm transition-colors py-1"
        >
          Bantuan
        </a>
      </div>

      <!-- Auth Actions -->
      <div class="flex items-center gap-6">
        <a 
          href="#" 
          class="text-[#000666] font-semibold text-sm hover:underline"
        >
          Masuk
        </a>
        <a 
          href="#" 
          class="bg-[#0b1b66] hover:bg-[#000666] text-white px-6 py-2 rounded-lg font-semibold text-sm transition-all shadow-sm"
        >
          Daftar
        </a>
      </div>
    </nav>
  </header>
</template>

<script setup>
// No complex reactive state needed for static landing
</script>