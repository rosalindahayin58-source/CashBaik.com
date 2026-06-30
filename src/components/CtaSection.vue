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
            Mulai Dapatkan Cashback Sekarang!
          </h2>

          <p class="text-blue-100 text-base md:text-lg mb-8 leading-relaxed">
            Bergabung dengan jutaan pengguna CashBaik dan dapatkan Cashback dari setiap belanja online.
          </p>


          <!-- App Download Badges -->
          <div class="flex flex-wrap justify-center md:justify-start gap-4">

            <!-- Play Store Badge -->
            <a 
              href="#" 
              class="flex items-center gap-2.5 bg-black hover:bg-zinc-900 text-white px-5 py-2.5 rounded-xl border border-zinc-800 transition-all shadow-md"
            >

              <!-- Play Icon -->
              <svg 
                class="w-6 h-6 fill-current" 
                viewBox="0 0 24 24" 
                xmlns="http://www.w3.org/2000/svg"
              >
                <path d="M5 3.23v17.54c0 .54.37.91.89.91.17 0 .34-.05.5-.16L18.45 13c.8-.5 1.45-1 .3-.37L6.68 3.5c-.17-.11-.34-.16-.5-.16-.52 0-.89.37-.89.91zM18.45 11l-2.73-1.58L6.68 18.72l9.04-9.3 2.73-1.58c.84-.49.84-1.28 0-1.76z" />
              </svg>


              <div class="text-left">
                <p class="text-[9px] uppercase tracking-wider text-gray-400">
                  GET IT ON
                </p>

                <p class="text-xs font-bold -mt-0.5">
                  Google Play
                </p>
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