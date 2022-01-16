<template>
  <div>
    <div class="relative">
      <header class="fixed w-full flex bg-black bg-opacity-40 items-center text-white p-4 backdrop-blur-sm z-10">
        <a href="/" class="flex items-center">
          <img
            src="/images/logo.svg"
            class="w-16"
            alt="Mercedes Benz"
          >
          <span class="font-Gelasio text-3xl ml-6">{{ $t('benz') }}</span>
        </a>
        <nav
          ref="menu"
          class="flex gap-x-7 ml-auto transition-opacity duration-200"
          :class="toggleSearch ? 'opacity-0' : null"
        >
          <a
            v-for="(item, i) in menuItems"
            :key="i"
            :href="'/' + item"
          >
            {{ $t(item) }}
          </a>
        </nav>
        <span class="material-icons mx-7 cursor-pointer" @click="toggleSearch = !toggleSearch">search</span>
        <a href="/deutsch">{{ $t('deutsch') }}</a>
      </header>
      <!-- slider -->
      <span class="absolute top-2/4 left-2 material-icons text-4xl text-white drop-shadow cursor-pointer">arrow_back_ios_new</span>
      <img
        src="/images/mercedes-benz-the-all-electric-eqe-2021-v295-3400x1440.jpeg"
        class="h-screen object-cover"
        alt="mercedes-benz-iaa-mobility-2021"
      >
      <h1 class="absolute top-56 left-20 text-4xl text-white font-Gelasio">
        The EQE.
      </h1>
      <a href="#" class="absolute top-72 left-20 bg-gray-700 text-white px-5 py-1.5">Learn more about the EQE</a>
      <span class="absolute top-2/4 right-2 material-icons text-4xl text-white drop-shadow cursor-pointer">arrow_forward_ios</span>
    </div>
    <main class="p-5">
      <nuxt />
    </main>
  </div>
</template>

<script>
export default {
  name: 'MainLayout',
  data () {
    return {
      menuItems: ['company', 'vehicles', 'design', 'innovation', 'museumAndHistory', 'sports', 'events', 'lifestyle'],
      toggleSearch: false
    }
  },
  methods: {
    openSearch () {

    }
  }
}
</script>

<style>

</style>
