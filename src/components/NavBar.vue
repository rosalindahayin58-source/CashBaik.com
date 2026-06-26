<template>
  <header ref="headerRef" class="fixed top-0 w-full z-50 bg-white border-b border-gray-100">
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
            'text-sm py-1 border-b-2 transition-colors duration-200',
            activeSection === link.id
              ? 'text-[#000666] font-semibold border-[#000666]'
              : 'text-gray-500 hover:text-[#000666] font-medium border-transparent'
          ]"
          @click.prevent="scrollToSection(link.id)"
        >
          {{ link.label }}
        </a>
      </div>

      <!-- Auth Actions -->
      <div class="flex items-center gap-6">
        <a
          href="#"
          class="text-[#000666] font-semibold text-sm hover:underline"
        >
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

const headerRef = ref(null)
const activeSection = ref('home')

const navLinks = [
  { id: 'home',     label: 'Home'     },
  { id: 'merchant', label: 'Merchant' },
  { id: 'promo',    label: 'Promo'    },
  { id: 'bantuan',  label: 'Bantuan'  },
]

// Smooth-scroll to a section, offsetting for the sticky header height
function scrollToSection(id) {
  const target = document.getElementById(id)
  if (!target) return
  const navHeight = headerRef.value?.offsetHeight ?? 0
  window.scrollTo({ top: target.offsetTop - navHeight, behavior: 'smooth' })
}

let observer = null

onMounted(() => {
  const navHeight = headerRef.value?.offsetHeight ?? 72

  // Each section becomes "active" as soon as its top edge enters the
  // detection band just below the navbar. The -60% bottom margin ensures
  // only the section dominating the upper viewport wins.
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id
        }
      })
    },
    {
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