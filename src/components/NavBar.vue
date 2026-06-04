<template>
  <nav class="navbar">
    <!-- Logo -->
    <div class="logo">
      <a href="#">
        <img src="/images/logo.jpg" alt="CashBaik Logo" />
      </a>
    </div>

    <!-- Nav Menu (desktop: flex, mobile: hidden sampai active) -->
    <div class="nav-menu" :class="{ active: menuOpen }" id="navMenu">
      <ul class="nav-links">
        <li><a href="#beranda"   :class="{ active: activeSection === 'beranda' }"   @click="closeMenu">Beranda</a></li>
        <li><a href="#cara-kerja" :class="{ active: activeSection === 'cara-kerja' }" @click="closeMenu">Cara Kerja</a></li>
        <li><a href="#merchant"  :class="{ active: activeSection === 'merchant' }"  @click="closeMenu">Merchant</a></li>
        <li><a href="#kontak"    :class="{ active: activeSection === 'kontak' }"    @click="closeMenu">Kontak</a></li>
      </ul>
      <div class="nav-right">
        <a href="https://cashbaik.com" target="_blank" class="btn-register" @click="closeMenu">Mulai Cashback</a>
      </div>
    </div>

    <!-- Hamburger (mobile only, ditaruh TERAKHIR agar flexbox push ke kanan) -->
    <div class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
      <i :class="menuOpen ? 'fas fa-times' : 'fas fa-bars'"></i>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen     = ref(false)
const activeSection = ref('beranda')

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function closeMenu() {
  menuOpen.value = false
}

// Tutup menu saat klik di luar navbar
function handleClickOutside(e) {
  const navbar = document.querySelector('.navbar')
  if (navbar && !navbar.contains(e.target)) {
    menuOpen.value = false
  }
}

// Tutup menu saat resize ke desktop
function handleResize() {
  if (window.innerWidth > 768) {
    menuOpen.value = false
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  document.removeEventListener('click', handleClickOutside)
  window.removeEventListener('resize', handleResize)
})
</script>