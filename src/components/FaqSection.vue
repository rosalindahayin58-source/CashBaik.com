<template>
  <!-- FAQ Section -->
  <section class="py-24 bg-surface">
    <div class="max-w-3xl mx-auto px-margin-mobile md:px-margin-desktop">
      <div class="text-center mb-16">
        <h2 class="font-headline-lg text-headline-lg text-primary mb-4">Pertanyaan Umum</h2>
        <p class="text-body-md text-on-surface-variant">Temukan jawaban untuk segala hal yang ingin Anda ketahui.</p>
      </div>

      <div class="space-y-4">
        <details
          v-for="(faq, index) in faqs"
          :key="index"
          class="group bg-surface-container-lowest border border-outline-variant/30 rounded-2xl overflow-hidden"
          :open="openIndex === index"
          @toggle="onToggle(index, $event)"
        >
          <summary class="flex justify-between items-center p-6 cursor-pointer list-none font-headline-md text-primary">
            <span>{{ faq.question }}</span>
            <span class="material-symbols-outlined group-open:rotate-180 transition-transform duration-300">expand_more</span>
          </summary>
          <div class="px-6 pb-6 text-body-md text-on-surface-variant">
            {{ faq.answer }}
          </div>
        </details>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const openIndex = ref(0)

const faqs = [
  {
    question: 'Apa itu CashBaik?',
    answer: 'CashBaik adalah platform cashback fintech terkemuka di Indonesia yang bermitra dengan ratusan marketplace dan toko online. Kami mengembalikan sebagian uang dari transaksi belanja Anda langsung ke saldo akun CashBaik yang bisa dicairkan ke rekening bank.',
  },
  {
    question: 'Bagaimana cara menarik saldo?',
    answer: 'Anda dapat menarik saldo setelah mencapai batas minimum penarikan Rp 50.000. Cukup masuk ke menu \'Tarik Saldo\', pilih rekening bank Anda, dan dana akan diproses dalam 1-3 hari kerja.',
  },
  {
    question: 'Apakah CashBaik aman digunakan?',
    answer: 'Ya, CashBaik menggunakan sistem keamanan tingkat bank dengan enkripsi SSL 256-bit untuk melindungi data Anda. Kami tidak pernah menyimpan detail login merchant Anda.',
  },
]

function onToggle(index, event) {
  const detail = event.target
  if (detail.open) {
    openIndex.value = index
    // Close other details
    document.querySelectorAll('details').forEach((other) => {
      if (other !== detail) other.removeAttribute('open')
    })
  }
}
</script>
