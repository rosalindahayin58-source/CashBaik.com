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
              class="inline-block transition-transform hover:scale-105 active:scale-95"
            >
              <img 
                src="/images/google-play-badge.svg" 
                alt="Get it on Google Play" 
                class="h-14 md:h-16 w-auto"
              />
            </a>
          </div>
        </div>

        <!-- Right Content -->
        <div class="z-10 flex flex-col items-center md:items-start">
          <a 
            href="https://affiliate-app.esoftdream.co.id/" 
            target="_blank"
            rel="noopener"
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