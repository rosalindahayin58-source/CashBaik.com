<template>
  <header class="fixed top-0 w-full z-50 bg-white border-b border-gray-100">
    <nav class="flex justify-between items-center px-6 md:px-12 py-4 max-w-7xl mx-auto">

      <!-- Logo -->
      <div class="flex items-center gap-2">
        <svg width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M 6 2 H 16 C 24 2, 28 6, 28 12 C 28 15, 25 16.5, 22 17 C 26 17.5, 30 20, 30 24 C 30 30, 24 30, 16 30 H 6 C 3.8 30, 2 28.2, 2 26 V 6 C 2 3.8, 3.8 2, 6 2 Z" fill="#1d2de3"/>
          <path d="M 11 21 C 11 11, 21 7, 25 9 C 29 11, 19 23, 11 21 Z" fill="white"/>
          <path d="M 11 21 C 11 27, 5 29, 3 27 C 1 25, 7 21, 11 21 Z" fill="white"/>
        </svg>
        <span class="font-bold text-2xl text-[#1d2de3] tracking-tight">
          CashBaik
        </span>
      </div>

      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center gap-8">
        <a
          v-for="menu in menus"
          :key="menu.id"
          href="#"
          @click.prevent="scrollToSection(menu.id)"
          :class="[
            'text-sm font-medium py-1 border-b-2 transition-all duration-300',
            activeSection === menu.id
              ? 'text-[#000666] border-[#000666]'
              : 'text-gray-500 border-transparent hover:text-[#000666]'
          ]"
        >
          {{ menu.label }}
        </a>
      </div>

      <!-- Desktop Auth -->
      <div class="hidden md:flex items-center gap-6">
        <a
          href="https://affiliate-app.esoftdream.co.id/"
          target="_blank"
          rel="noopener"
          class="text-[#000666] font-semibold text-sm hover:underline"
        >
          Login
        </a>

        <a
          href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share"
          target="_blank"
          rel="noopener"
          class="bg-[#0b1b66] hover:bg-[#000666] text-white px-6 py-2 rounded-lg font-semibold text-sm transition-all shadow-sm"
        >
          Download
        </a>
      </div>

      <!-- Hamburger Button (Mobile/Tablet) -->
      <button
        @click="toggleMenu"
        class="md:hidden relative w-10 h-10 flex flex-col items-center justify-center gap-1.5 rounded-lg hover:bg-gray-100 transition-colors focus:outline-none"
        aria-label="Toggle menu"
        :aria-expanded="isMenuOpen"
      >
        <span
          :class="[
            'block w-6 h-0.5 bg-[#0b1b66] rounded-full transition-all duration-300 ease-in-out',
            isMenuOpen ? 'rotate-45 translate-y-[4px]' : ''
          ]"
        ></span>
        <span
          :class="[
            'block w-6 h-0.5 bg-[#0b1b66] rounded-full transition-all duration-300 ease-in-out',
            isMenuOpen ? 'opacity-0 scale-x-0' : 'opacity-100 scale-x-100'
          ]"
        ></span>
        <span
          :class="[
            'block w-6 h-0.5 bg-[#0b1b66] rounded-full transition-all duration-300 ease-in-out',
            isMenuOpen ? '-rotate-45 -translate-y-[4px]' : ''
          ]"
        ></span>
      </button>
    </nav>

    <!-- Mobile Menu Overlay -->
    <Transition name="fade">
      <div
        v-if="isMenuOpen"
        class="fixed inset-0 top-[65px] bg-black/30 backdrop-blur-sm z-40 md:hidden"
        @click="closeMenu"
      ></div>
    </Transition>

    <!-- Mobile Menu Panel -->
    <Transition name="slide-down">
      <div
        v-if="isMenuOpen"
        class="absolute top-full left-0 right-0 bg-white border-b border-gray-200 shadow-xl z-50 md:hidden"
      >
        <div class="flex flex-col px-6 py-4 gap-1">
          <!-- Navigation Links -->
          <a
            v-for="menu in menus"
            :key="menu.id"
            href="#"
            @click.prevent="scrollToSection(menu.id); closeMenu()"
            :class="[
              'px-4 py-3 rounded-xl text-sm font-medium transition-all duration-200',
              activeSection === menu.id
                ? 'bg-[#e0e7ff] text-[#000666] font-semibold'
                : 'text-gray-600 hover:bg-gray-50 hover:text-[#000666]'
            ]"
          >
            {{ menu.label }}
          </a>

          <!-- Divider -->
          <div class="my-2 border-t border-gray-100"></div>

          <!-- Auth Links -->
          <a
            href="https://affiliate-app.esoftdream.co.id/"
            target="_blank"
            rel="noopener"
            class="px-4 py-3 rounded-xl text-sm font-semibold text-[#000666] hover:bg-gray-50 transition-all duration-200"
          >
            Login
          </a>

          <a
            href="https://affiliate-app.esoftdream.co.id/"
            target="_blank"
            rel="noopener"
            class="mx-4 mt-1 mb-2 bg-[#ffd54a] hover:bg-yellow-500 text-[#0b1b66] font-bold px-6 py-3 rounded-xl shadow-md text-center text-sm transition-all"
          >
            Daftar Sekarang
          </a>

          <a
            href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share"
            target="_blank"
            rel="noopener"
            class="mx-4 mb-2 bg-[#0b1b66] hover:bg-[#000666] text-white font-semibold px-6 py-3 rounded-xl shadow-md text-center text-sm transition-all"
          >
            Download App
          </a>
        </div>
      </div>
    </Transition>
  </header>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const activeSection = ref("home");
const isMenuOpen = ref(false);

const menus = [
  {
    id: "home",
    label: "Home",
  },
  {
    id: "merchant",
    label: "Merchant",
  },
  {
    id: "promo",
    label: "Promo",
  },
  {
    id: "bantuan",
    label: "Bantuan",
  },
];

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const closeMenu = () => {
  isMenuOpen.value = false;
};

const scrollToSection = (id) => {
  const section = document.getElementById(id);

  if (section) {
    section.scrollIntoView({
      behavior: "smooth",
      block: "start",
    });
  }
};

// Close menu on resize to desktop
const handleResize = () => {
  if (window.innerWidth >= 768) {
    closeMenu();
  }
};

let observer = null;

onMounted(() => {
  window.addEventListener("resize", handleResize);

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id;
        }
      });
    },
    {
      root: null,
      threshold: 0.5,
    }
  );

  menus.forEach((menu) => {
    const section = document.getElementById(menu.id);

    if (section) {
      observer.observe(section);
    }
  });
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", handleResize);

  if (observer) {
    observer.disconnect();
  }
});
</script>

<style scoped>
/* Mobile menu slide-down transition */
.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
  transform-origin: top;
}

.slide-down-enter-from,
.slide-down-leave-to {
  opacity: 0;
  transform: translateY(-8px) scaleY(0.96);
}

.slide-down-enter-to,
.slide-down-leave-from {
  opacity: 1;
  transform: translateY(0) scaleY(1);
}

/* Overlay fade transition */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}
</style>