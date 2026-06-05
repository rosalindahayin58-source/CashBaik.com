<template>
  <button
    v-if="isVisible"
    class="back-to-top"
    @click="scrollToTop"
  >
    ↑
  </button>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const isVisible = ref(false)

function handleScroll() {
  isVisible.value = window.scrollY > 300
}

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onBeforeUnmount(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.back-to-top {
  position: fixed;
  bottom: 30px;
  right: 30px;
  width: 45px;
  height: 45px;
  background: var(--primary);
  color: #fff;
  border: none;
  border-radius: 50%;
  font-size: 20px;
  cursor: pointer;
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  transition: .3s;
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
}

.back-to-top:hover {
  background: var(--secondary);
  transform: translateY(-3px);
}
</style>