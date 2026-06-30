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
          
          <!-- App Download Badges -->
          <div class="flex flex-wrap justify-center md:justify-start gap-4">
            <!-- App Store Badge -->
            <a 
              href="#" 
              class="flex items-center gap-2.5 bg-black hover:bg-zinc-900 text-white px-5 py-2.5 rounded-xl border border-zinc-800 transition-all shadow-md"
            >
              <!-- Apple Icon -->
              <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M18.71 19.5C17.88 20.74 17 21.95 15.66 21.97C14.32 22 13.89 21.18 12.37 21.18C10.84 21.18 10.37 21.95 9.1 22C7.79 22.05 6.8 20.68 5.96 19.48C4.25 17 2.94 12.45 4.7 9.39C5.57 7.87 7.13 6.91 8.82 6.88C10.1 6.86 11.32 7.75 12.11 7.75C12.89 7.75 14.37 6.68 15.92 6.84C16.57 6.87 18.39 7.1 19.56 8.82C19.47 8.88 17.39 10.1 17.41 12.63C17.44 15.65 20.06 16.66 20.1 16.67C20.08 16.74 19.67 18.11 18.71 19.5M15.97 4.17C16.63 3.37 17.07 2.28 16.95 1C15.85 1.04 14.51 1.73 13.73 2.64C13.07 3.41 12.49 4.52 12.64 5.78C13.87 5.87 15.12 5.17 15.97 4.17Z" />
              </svg>
              <div class="text-left">
                <p class="text-[9px] uppercase tracking-wider text-gray-400">Download on the</p>
                <p class="text-xs font-bold -mt-0.5">App Store</p>
              </div>
            </a>

            <!-- Play Store Badge -->
            <a 
              href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share" 
              target="_blank"
              rel="noopener"
              class="flex items-center gap-2.5 bg-black hover:bg-zinc-900 text-white px-5 py-2.5 rounded-xl border border-zinc-800 transition-all shadow-md"
            >
              <!-- Play Icon -->
              <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M5 3.23v17.54c0 .54.37.91.89.91.17 0 .34-.05.5-.16L18.45 13c.8-.5 1.45-1 .3-.37L6.68 3.5c-.17-.11-.34-.16-.5-.16-.52 0-.89.37-.89.91zM18.45 11l-2.73-1.58L6.68 18.72l9.04-9.3 2.73-1.58c.84-.49.84-1.28 0-1.76z" />
              </svg>
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