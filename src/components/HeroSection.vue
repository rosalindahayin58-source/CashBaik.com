<template>
  <section class="relative bg-gradient-to-tr from-[#f8fafc] to-[#e0e7ff] pt-28 pb-16 overflow-hidden" id="home">
    <!-- Hero Main Container -->
    <div class="max-w-7xl mx-auto px-6 md:px-12 grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <!-- Left Content -->
      <div class="z-10 flex flex-col items-start">
        <!-- Trust Badge -->
        <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-[#e0e7ff] text-[#0b1b66] font-semibold text-xs mb-6 shadow-sm">
          <span>🛡️</span>
          <span>Gratis & Terpercaya</span>
        </div>

        <!-- Headline -->
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-[#0b1b66] tracking-tight leading-tight mb-6">
          Dapatkan Cashback Terbaikmu, 
          <div class="inline-flex flex-wrap gap-2 items-center mt-2">
            <span class="bg-[#0b1b66] text-[#ffd54a] px-3 py-1 rounded-xl shadow-md">dengan</span>
            <span class="bg-[#ffd54a] text-[#0b1b66] px-3 py-1 rounded-xl shadow-md">CashBaik</span>
          </div>
        </h1>

        <!-- Subtitle -->
        <p class="text-gray-600 text-lg leading-relaxed mb-8 max-w-xl">
          Dapatkan cashback hingga 30% dari berbagai merchant favoritmu. Belanja seperti biasa, tabungan bertambah otomatis.
        </p>

        <!-- Call to Action Buttons -->
        <div class="flex flex-wrap gap-4 mb-4">
          <a 
            href="https://affiliate-app.esoftdream.co.id/" 
            target="_blank"
            rel="noopener"
            class="bg-[#ffd54a] hover:bg-yellow-500 text-[#0b1b66] font-bold px-8 py-3.5 rounded-2xl shadow-lg transition-all transform hover:-translate-y-0.5 active:translate-y-0"
          >
            Daftar Sekarang
          </a>
          <a 
            href="#cara-kerja" 
            class="bg-white hover:bg-gray-50 text-[#0b1b66] font-semibold px-8 py-3.5 rounded-2xl border border-gray-200 shadow-sm transition-all transform hover:-translate-y-0.5 active:translate-y-0"
          >
            Cara Kerja
          </a>
        </div>
      </div>

      <!-- Right Visual (Hero Image and floating card) -->
      <div class="relative flex justify-center lg:justify-end items-center">
        <!-- Background Blur Graphic -->
        <div class="absolute w-[400px] h-[400px] bg-blue-300/30 rounded-full blur-3xl -z-10"></div>
        
        <div class="relative w-full max-w-md">
          <!-- Main Hero Image -->
          <img 
            class="w-full h-[480px] object-cover rounded-[32px] shadow-2xl border border-white/20"
            alt="Belanja Hemat CashBaik" 
            src="/images/hero_woman_shopping.png"
          />

          <!-- Floating Reward Banner -->
          <div class="absolute bottom-6 left-6 right-6 glass-card p-4 rounded-2xl shadow-xl border border-white/40 flex items-center gap-4">
            <div class="w-12 h-12 rounded-full bg-[#0b1b66] flex items-center justify-center flex-shrink-0">
              <!-- Wallet Card Material Icon -->
              <span class="material-symbols-outlined text-[#ffd54a]" style="font-variation-settings: 'FILL' 1;">account_balance_wallet</span>
            </div>
            <div>
              <p class="text-xs text-gray-500 font-medium">Total Reward Terkumpul</p>
              <p class="text-xl font-bold text-[#0b1b66]">Rp 12.450.000</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Ticker Running Text Banner -->
    <div class="w-full bg-[#0b1b66] py-3 mt-16 overflow-hidden whitespace-nowrap border-y border-blue-950">
      <div class="inline-block animate-ticker text-sm font-semibold text-white/90">
        <span class="mx-8">• Budi S. baru saja mencairkan Rp 250.000 ke GoPay</span>
        <span class="mx-8">• Anita W. mendapatkan cashback Rp 45.000 dari GrabFood</span>
        <span class="mx-8">• Rian M. baru saja mendaftar di CashBaik</span>
        <span class="mx-8">• Budi S. baru saja mencairkan Rp 250.000 ke GoPay</span>
        <span class="mx-8">• Anita W. mendapatkan cashback Rp 45.000 dari GrabFood</span>
        <span class="mx-8">• Rian M. baru saja mendaftar di CashBaik</span>
      </div>
    </div>
  </section>
</template>

<script setup>
// Static presentation of hero section
</script>

<style scoped>
@keyframes ticker {
  0% { transform: translate3d(0, 0, 0); }
  100% { transform: translate3d(-50%, 0, 0); }
}
.animate-ticker {
  display: inline-block;
  animation: ticker 25s linear infinite;
}
</style>