<template>
  <section class="cta-section" id="mulai">
    <h2>Klaim promonya Sekarang <span class="rocket">🔥</span></h2>
    <p>
      Bergabunglah bersama 50.000+ pengguna yang sudah merasakan manfaat
      cashback dari CashBaik setiap harinya.
    </p>
    <div class="cta-buttons">
      <a href="https://cashbaik.com/" class="cta-button primary-cta" target="_blank" rel="noopener">
        Kunjungi Website
      </a>
      <a href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share" class="cta-button secondary-cta" target="_blank" rel="noopener">
        Download Sekarang
      </a>
    </div>
  </section>
</template>

<script setup>
// No logic needed for static CTA
</script>

<style scoped>
@keyframes rocketLaunch {
  0%   { transform: translateY(0px); }
  30%  { transform: translateY(-12px); }
  60%  { transform: translateY(-6px); }
  100% { transform: translateY(0px); }
}

.rocket {
  display: inline-block;
  animation: rocketLaunch 1.5s ease-in-out infinite;
}
</style>