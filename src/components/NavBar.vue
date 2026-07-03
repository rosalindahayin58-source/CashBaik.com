<template>
  <header class="fixed top-0 w-full z-50 bg-white border-b border-gray-100">
    <nav class="flex justify-between items-center px-6 md:px-12 py-4 max-w-7xl mx-auto">

      <!-- Logo -->
      <div class="flex items-center gap-2">
        <span class="font-bold text-2xl text-[#000666] tracking-tight">
          CashBaik
        </span>
      </div>

      <!-- Navigation -->
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

      <!-- Auth -->
      <div class="flex items-center gap-6">
        <a
          href="#"
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

    </nav>
  </header>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const activeSection = ref("home");

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

const scrollToSection = (id) => {
  const section = document.getElementById(id);

  if (section) {
    section.scrollIntoView({
      behavior: "smooth",
      block: "start",
    });
  }
};

let observer = null;

onMounted(() => {
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
  if (observer) {
    observer.disconnect();
  }
});
</script>