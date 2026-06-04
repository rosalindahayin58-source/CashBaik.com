<template>
  <section class="merchant-section" id="merchant">
    <div class="section-header">
      <h2>Merchant Populer</h2>
      <p>Belanja di ratusan merchant favorit dan nikmati cashback eksklusif.</p>
    </div>

    <div ref="splideEl" class="splide" aria-label="Merchant Populer">
      <div class="splide__track">
        <ul class="splide__list">
          <li
            v-for="(merchant, index) in merchants"
            :key="index"
            class="splide__slide"
          >
            <div class="merchant-card">
              <div class="merchant-icon">
                <img :src="merchant.logo" :alt="merchant.name" />
              </div>
              <h3>{{ merchant.name }}</h3>
              <p>{{ merchant.cashback }}</p>
              <a :href="merchant.url" class="merchant-btn" target="_blank" rel="noopener">
                Belanja Sekarang
              </a>
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

const merchants = [
  {
    name: 'Shopee',
    logo: '/merchants/shopee.png',
    cashback: 'Nikmati voucher gratis ongkir tanpa minimal belanja.',
    url: '#',
  },
  {
    name: 'Tokopedia',
    logo: '/merchants/tokopedia.png',
    cashback: 'Nikmati cashback hingga Rp 500.000 untuk transaksi pembayaran tertentu..',
    url: '#',
  },
  {
    name: 'Lazada',
    logo: '/merchants/lazada.png',
    cashback: 'Pantau jadwal flash sale setiap harinya untuk mendapatkan barang dengan harga terendah dalam waktu terbatas.',
    url: '#',
  },
]

onMounted(async () => {
  const { default: Splide } = await import('@splidejs/splide')

  splideInstance = new Splide(splideEl.value, {
    type: 'loop',
    perPage: 3,
    perMove: 1,
    gap: '20px',
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