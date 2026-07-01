<template>
  <header 
    ref="headerRef" 
    class="fixed top-0 w-full z-50 bg-white border-b border-gray-100"
  >

    <nav class="flex justify-between items-center px-6 lg:px-12 py-4 max-w-7xl mx-auto">


      <!-- Logo -->
      <div class="flex items-center gap-2">
        <span class="font-bold text-2xl text-[#000666] tracking-tight">
          CashBaik
        </span>
      </div>



      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center gap-8">

        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          :class="[
            'text-sm py-1 border-b-2 transition-colors duration-200',
            activeSection === link.id
              ? 'text-[#000666] font-semibold border-[#000666]'
              : 'text-gray-500 hover:text-[#000666] border-transparent'
          ]"
          @click.prevent="scrollToSection(link.id)"
        >
          {{ link.label }}
        </a>

      </div>




      <!-- Desktop Button -->
      <div class="hidden md:flex items-center gap-6">


        <!-- Login -->
        <a
          href="https://affiliate-app.esoftdream.co.id/"
          target="_blank"
          class="text-[#000666] font-semibold text-sm hover:underline"
        >
          Login
        </a>



        <!-- Download -->
        <a
          href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share
          @click.prevent="scrollToSection('download')"
          class="bg-[#0b1b66] hover:bg-[#000666] text-white px-6 py-2 rounded-lg font-semibold text-sm transition-all shadow-sm"
        >
          Download
        </a>


      </div>






      <!-- Mobile Button -->
      <div class="flex md:hidden items-center gap-3">


        <!-- Login -->
        <a
          href="https://affiliate-app.esoftdream.co.id/"
          target="_blank"
          class="text-[#000666] font-semibold text-sm"
        >
          Login
        </a>



        <!-- Download -->
        <a
          href="#download"
          @click.prevent="scrollToSection('download')"
          class="bg-[#0b1b66] text-white px-4 py-1.5 rounded-lg font-semibold text-sm"
        >
          Download
        </a>





        <!-- Hamburger -->
        <button
          @click="toggleMenu"
          class="ml-1 p-1.5 rounded-md text-[#000666]"
        >

          <svg
            v-if="!menuOpen"
            xmlns="http://www.w3.org/2000/svg"
            class="w-6 h-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >

            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />

          </svg>




          <svg
            v-else
            xmlns="http://www.w3.org/2000/svg"
            class="w-6 h-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >

            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />

          </svg>


        </button>


      </div>

    </nav>






    <!-- Mobile Menu -->
    <transition>

      <div
        v-if="menuOpen"
        class="md:hidden bg-white border-t px-6 py-4 shadow-lg"
      >

        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          @click.prevent="mobileScrollToSection(link.id)"
          class="block py-3 text-gray-600 hover:text-[#000666]"
        >

          {{ link.label }}

        </a>


      </div>


    </transition>



  </header>
</template>






<script setup>

import { ref } from 'vue'


const headerRef = ref(null)

const activeSection = ref('home')

const menuOpen = ref(false)



const navLinks = [

  {
    id:'home',
    label:'Home'
  },

  {
    id:'merchant',
    label:'Merchant'
  },

  {
    id:'promo',
    label:'Promo'
  },

  {
    id:'bantuan',
    label:'Bantuan'
  }

]





function toggleMenu(){

  menuOpen.value = !menuOpen.value

}





function scrollToSection(id){


  const target = document.getElementById(id)


  if(!target) return



  const headerHeight = headerRef.value?.offsetHeight || 80



  window.scrollTo({

    top: target.offsetTop - headerHeight,

    behavior:'smooth'

  })


}






function mobileScrollToSection(id){


  menuOpen.value = false



  setTimeout(()=>{

    scrollToSection(id)

  },150)


}


</script>