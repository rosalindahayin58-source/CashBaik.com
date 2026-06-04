<template>
  <footer class="footer" id="kontak">
    <div class="footer-grid">
      <!-- Brand col -->
      <div class="footer-col footer-col-brand">
        <img src="/images/logo.jpg" alt="CashBaik Logo" class="footer-logo" />
        <p>
          Platform cashback terpercaya untuk belanja online lebih hemat
          di berbagai marketplace Indonesia.
        </p>
      </div>

      <!-- Links col -->
      <div class="footer-col">
        <h4>Navigasi</h4>
        <a href="#beranda">Beranda</a>
        <a href="#cara-kerja">Cara Kerja</a>
        <a href="#merchant">Merchant</a>
        <a href="#mulai">Daftar</a>
      </div>

      <!-- Support col -->
      <div class="footer-col">
        <h4>Bantuan</h4>
        <a href="#">FAQ</a>
        <a href="#">Syarat & Ketentuan</a>
        <a href="#">Kebijakan Privasi</a>
        <a href="#">Hubungi Kami</a>
      </div>

      <!-- Contact col -->
      <div class="footer-col">
        <h4>Kontak</h4>
        <p>
          <i class="fas fa-envelope"></i>
          support@cashbaik.id
        </p>
        <p>
          <i class="fab fa-whatsapp"></i>
          +62 812-3456-7890
        </p>
        <p>
          <i class="fas fa-map-marker-alt"></i>
          Jakarta, Indonesia
        </p>
      </div>
    </div>

    <div class="footer-bottom">
      <p>&copy; {{ currentYear }} CashBaik. All Rights Reserved.</p>
    </div>
  </footer>
</template>

<script setup>
import { computed } from 'vue'

const currentYear = computed(() => new Date().getFullYear())
</script>