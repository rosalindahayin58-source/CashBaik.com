<template>
  <section class="how-it-works" id="cara-kerja">
    <div class="section-header">
      <h2>Bagaimana Cara Kerja CashBaik?</h2>
      <p>CashBaik adalah aplikasi yang dirancang untuk membantu Anda mengelola keuangan pribadi dengan mudah dan efisiensi.Berikut adalah cara kerja utama dari CashBaik.</p>
    </div>

    <div ref="splideEl" class="splide" aria-label="Cara Kerja CashBaik">
      <div class="splide__track">
        <ul class="splide__list">
          <li
            v-for="(step, index) in steps"
            :key="index"
            class="splide__slide"
          >
            <div class="step-card">
              <div class="step-icon">
                <span class="step-emoji">{{ step.emoji }}</span>
                <span>{{ step.number }}</span>
              </div>
              <h4>{{ step.title }}</h4>
              <p>{{ step.desc }}</p>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const splideEl = ref(null)
let splideInstance = null

const steps = [
  {
    number: 1,
    emoji: '🔗',
    title: 'Salin Link Produk dari Marketplace favoritmu.',
    desc: 'Salin link produk yang ingin Anda beli dari berbagai marketplace seperti Tokopedia, Shopee, Lazada, Bukalapak, Blibli, JDID, TikTok Shop, dan lainnya.',
  },
  {
    number: 2,
    emoji: '📱',
    title: 'Buka CashBaik',
    desc: 'CashBaik otomatis mendapatkan link dari clipboard dan Cashback akan membawa kamu ke halaman detil produk.',
  },
  {
    number: 3,
    emoji: '🛒',
    title: 'Tekan "Beli di Marketplace"',
    desc: 'Cukup tekan tombol "Beli di Marketplace" dan kamu akan diarahkan langsung ke aplikasinya.',
  },
  {
    number: 4,
    emoji: '✅',
    title: 'Cashback Diterima',
    desc: 'Setelah transaksi selesai, cashback otomatis masuk ke akun CashBaik kamu.',
  },
  {
    number: 5,
    emoji: '💰',
    title: 'Tarik Saldo',
    desc: 'Tarik saldo cashback-mu ke rekening bank atau e-wallet kapan saja kamu mau.',
  },
]

onMounted(async () => {
  const { default: Splide } = await import('@splidejs/splide')
  await import('@splidejs/splide/css')

  splideInstance = new Splide(splideEl.value, {
    type: 'loop',
    perPage: 3,
    perMove: 1,
    gap: '20px',
    padding: { left: 0, right: 0 },
    pagination: true,
    arrows: true,
    breakpoints: {
      900: { perPage: 2 },
      600: { perPage: 1 },
    },
  })

  splideInstance.mount()
})

onBeforeUnmount(() => {
  if (splideInstance) splideInstance.destroy()
})
</script>

<style scoped>
.step-emoji {
  font-size: 28px;
  line-height: 1;
}
</style>git add src/components/MerchantSection.vuegit add src/components/MerchantSection.vuegit add src/components/MerchantSection.vue