<template>
  <nav class="navbar">
    <div class="logo">
      <a href="#beranda">
        <img src="/images/logo.jpg" alt="CashBaik Logo" />
      </a>
    </div>

    <div class="hamburger" @click="toggleMenu">
      <i class="fas fa-bars"></i>
    </div>

    <div class="nav-menu" :class="{ active: menuOpen }">
      <ul class="nav-links">
        <li><a href="#beranda" :class="{ active: activeSection === 'beranda' }" @click="closeMenu">Beranda</a></li>
        <li><a href="#cara-kerja" :class="{ active: activeSection === 'cara-kerja' }" @click="closeMenu">Cara Kerja</a></li>
        <li><a href="#merchant" :class="{ active: activeSection === 'merchant' }" @click="closeMenu">Merchant</a></li>
        <li><a href="#kontak" :class="{ active: activeSection === 'kontak' }" @click="closeMenu">Kontak</a></li>
      </ul>
      <div class="nav-right">
        <a href="https://cashbaik.com/" class="btn-register" target="_blank" rel="noopener">Mulai Cashback</a>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const menuOpen = ref(false)
const activeSection = ref('beranda')

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function closeMenu() {
  menuOpen.value = false
}

let observer = null

onMounted(() => {
  const sections = ['beranda', 'cara-kerja', 'merchant', 'kontak']

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id
        }
      })
    },
    {
      rootMargin: '-50% 0px -50% 0px',
      threshold: 0,
    }
  )

  sections.forEach((id) => {
    const el = document.getElementById(id)
    if (el) observer.observe(el)
  })
})

onBeforeUnmount(() => {
  if (observer) observer.disconnect()
})
</script>