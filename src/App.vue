<template>
  <div class="min-h-screen bg-white">
    <NavBar />
    <HeroSection />
    <MerchantSection />
    <HowItWorks />
    <CtaSection />
    <FooterSection />
    <BackToTop />
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import MerchantSection from './components/MerchantSection.vue'
import HowItWorks from './components/HowItWorks.vue'
import CtaSection from './components/CtaSection.vue'
import FooterSection from './components/FooterSection.vue'
import BackToTop from './components/BackToTop.vue'
</script>