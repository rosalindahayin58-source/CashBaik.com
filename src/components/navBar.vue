<template>
  <nav class="navbar">
    <!-- Logo -->
    <div class="logo">
      <a href="#">
        <img src="/images/logo.jpg" alt="CashBaik Logo" />
        <!-- Fallback text logo if image not found -->
      </a>
    </div>

    <!-- Hamburger (mobile) -->
    <div class="hamburger" @click="toggleMenu">
      <i class="fas fa-bars"></i>
    </div>

    <!-- Nav Menu -->
    <div class="nav-menu" :class="{ active: menuOpen }">
      <ul class="nav-links">
        <li><a href="#beranda" :class="{ active: activeSection === 'beranda' }" @click="closeMenu">Beranda</a></li>
        <li><a href="#cara-kerja" :class="{ active: activeSection === 'cara-kerja' }" @click="closeMenu">Cara Kerja</a></li>
        <li><a href="#merchant" :class="{ active: activeSection === 'merchant' }" @click="closeMenu">Merchant</a></li>
        <li><a href="#kontak" :class="{ active: activeSection === 'kontak' }" @click="closeMenu">Kontak</a></li>
      </ul>
      <div class="nav-right">
        <a href="#mulai" class="btn-register" @click="closeMenu">Mulai Cashback</a>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)
const activeSection = ref('beranda')

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function closeMenu() {
  menuOpen.value = false
}
</script>