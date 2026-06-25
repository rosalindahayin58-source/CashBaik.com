<template>
  <!-- Referral Banner -->
  <section class="py-16">
    <div class="max-w-container-max mx-auto px-margin-mobile md:px-margin-desktop">
      <div class="bg-primary rounded-3xl p-8 md:p-16 relative overflow-hidden flex flex-col lg:flex-row items-center justify-between gap-12">
        <!-- Background decoration -->
        <div class="absolute top-0 right-0 w-1/2 h-full opacity-10"></div>

        <!-- Left content -->
        <div class="z-10 text-center lg:text-left max-w-xl">
          <h2 class="font-display-lg text-display-lg text-white mb-6">
            Ajak Teman &amp; <br />
            Dapat Bonus <span class="text-secondary-container">50rb</span>
          </h2>
          <p class="text-body-lg text-white/80 mb-10">
            Undang temanmu untuk bergabung dan dapatkan bonus saldo instan untuk setiap teman yang berbelanja pertama kali.
          </p>
          <button class="bg-secondary-container text-on-secondary-container px-10 py-4 rounded-xl font-headline-md font-bold hover:scale-105 active:scale-95 transition-all shadow-xl">
            Undang Sekarang
          </button>
        </div>

        <!-- Right referral progress card -->
        <div class="z-10 glass-card p-8 rounded-3xl border border-white/20 w-full max-w-sm">
          <div class="mb-6">
            <div class="flex justify-between items-end mb-2">
              <span class="text-label-sm text-primary font-bold">Referral Progress</span>
              <span class="text-label-md font-bold text-primary">8/10 Teman</span>
            </div>
            <div class="w-full h-3 bg-surface-container rounded-full overflow-hidden">
              <div class="w-4/5 h-full bg-secondary-container transition-all duration-1000"></div>
            </div>
          </div>

          <div class="space-y-4">
            <div class="flex items-center gap-3 p-3 bg-white/50 rounded-xl">
              <div class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center">
                <span class="material-symbols-outlined text-primary text-sm">person</span>
              </div>
              <div>
                <p class="text-label-sm font-bold text-primary">Budi Santoso</p>
                <p class="text-[10px] text-green-600 font-bold">+Rp 50.000 Terverifikasi</p>
              </div>
            </div>

            <div class="flex items-center gap-3 p-3 bg-white/50 rounded-xl">
              <div class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center">
                <span class="material-symbols-outlined text-primary text-sm">person</span>
              </div>
              <div>
                <p class="text-label-sm font-bold text-primary">Siti Aminah</p>
                <p class="text-[10px] text-primary/60 font-bold italic">Menunggu Transaksi</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Static referral banner
</script>
