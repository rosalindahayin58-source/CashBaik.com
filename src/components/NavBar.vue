<template>
  <header class="fixed top-0 w-full z-50 bg-white border-b border-gray-100">
    <nav class="flex justify-between items-center px-6 md:px-12 py-4 max-w-7xl mx-auto">
      <!-- Logo -->
      <div class="flex items-center gap-2">
        <span class="font-bold text-2xl text-[#000666] tracking-tight">CashBaik</span>
      </div>

      <!-- Navigation Links -->
      <div class="hidden md:flex items-center gap-8">
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          :class="[
            'font-medium text-sm transition-colors py-1 border-b-2',
            activeSection === link.id
              ? 'text-[#000666] font-semibold border-[#000666]'
              : 'text-gray-500 hover:text-[#000666] border-transparent'
          ]"
          @click.prevent="scrollToSection(link.id)"
        >
          {{ link.label }}
        </a>
      </div>

      <!-- Auth Actions -->
      <div class="flex items-center gap-6">
        <a href="#" class="text-[#000666] font-semibold text-sm hover:underline">
          Masuk
        </a>
        <a
          href="#"
          class="bg-[#0b1b66] hover:bg-[#000666] text-white px-6 py-2 rounded-lg font-semibold text-sm transition-all shadow-sm"
        >
          Daftar
        </a>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const navLinks = [
  { id: 'home',     label: 'Home'    },
  { id: 'merchant', label: 'Merchant'},
  { id: 'promo',    label: 'Promo'   },
  { id: 'bantuan',  label: 'Bantuan' },
]

const activeSection = ref('home')

let observer = null

function scrollToSection(id) {
  const el = document.getElementById(id)
  if (!el) return
  const navHeight = document.querySelector('header').offsetHeight
  window.scrollTo({ top: el.offsetTop - navHeight, behavior: 'smooth' })
}

onMounted(() => {
  const navHeight = document.querySelector('header').offsetHeight

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id
        }
      })
    },
    {
      // Top offset = navbar height so detection starts below it.
      // Bottom -60% means a section activates when it fills the top 40% of the screen.
      rootMargin: `-${navHeight}px 0px -60% 0px`,
      threshold: 0,
    }
  )

  navLinks.forEach(({ id }) => {
    const el = document.getElementById(id)
    if (el) observer.observe(el)
  })
})

onBeforeUnmount(() => {
  observer?.disconnect()
})
</script>