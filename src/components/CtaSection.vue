<template>
  <section class="py-16 bg-white" id="promo">
    <div class="max-w-7xl mx-auto px-6 md:px-12">
      <!-- Container Box -->
      <div class="bg-[#0b1b66] rounded-3xl p-8 md:p-16 relative overflow-hidden flex flex-col md:flex-row justify-between items-center gap-12 shadow-xl">
        <!-- Dots Background Pattern -->
        <div class="absolute inset-0 opacity-10 bg-[radial-gradient(#fff_1px,transparent_1px)] [background-size:16px_16px] pointer-events-none"></div>

        <!-- Left Content -->
        <div class="z-10 text-center md:text-left max-w-xl">
          <h2 class="text-3xl md:text-4xl lg:text-5xl font-extrabold text-white mb-6">
            Siap untuk untung terus?
          </h2>
          <p class="text-blue-100 text-base md:text-lg mb-8 leading-relaxed">
            Gabung dengan ribuan pengguna cerdas lainnya yang sudah menikmati cashback setiap hari.
          </p>
          
          <!-- App Download Badge -->
          <div class="flex justify-center md:justify-start">
            <!-- Play Store Badge -->
            <a 
              href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share" 
              target="_blank"
              rel="noopener"
              class="flex items-center gap-2.5 bg-black hover:bg-zinc-900 text-white px-5 py-2.5 rounded-xl border border-zinc-800 transition-all shadow-md"
            >
              <img src="/public/images/google-play-icon.png" alt="Google Play" class="w-6 h-6" />
              <div class="text-left">
                <p class="text-[9px] uppercase tracking-wider text-gray-400">GET IT ON</p>
                <p class="text-xs font-bold -mt-0.5">Google Play</p>
              </div>
            </a>
          </div>
        </div>

        <!-- Right Content -->
        <div class="z-10 flex flex-col items-center md:items-start">
          <a 
            href="#" 
            class="bg-[#ffd54a] hover:bg-yellow-500 text-[#0b1b66] font-extrabold px-10 py-4 rounded-2xl shadow-xl transition-all transform hover:-translate-y-0.5 active:translate-y-0 text-center w-full md:w-auto"
          >
            Daftar Sekarang
          </a>
          <p class="text-blue-200 text-xs mt-3 text-center md:text-left">
            Gratis selamanya, tanpa biaya admin!
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Static presentation
</script>