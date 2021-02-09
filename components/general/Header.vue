<template>
  <nav class="">
    <div class="relative flex items-center justify-between sm:h-16">
      <div class="absolute top-0 right-0 flex items-center sm:hidden">
        <!-- Mobile menu button-->
        <button
          @click="isOpen"
          class="inline-flex items-start justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
          aria-expanded="false"
        >
          <span class="sr-only">Open main menu</span>
          <!-- Icon when menu is closed. -->
          <!--
            Heroicon name: outline/menu

            Menu open: "hidden", Menu closed: "block"
          -->
          <svg
            class="h-6 w-6 inline-block"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            aria-hidden="true"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <!-- Icon when menu is open. -->
          <!--
            Heroicon name: outline/x

            Menu open: "block", Menu closed: "hidden"
          -->
          <svg
            class="hidden h-6 w-6"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            aria-hidden="true"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      <div class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start">
        <div class="hidden sm:block sm:ml-6">
          <div class="flex space-x-4">
            <ul class="flex fixed top-0 inset-x-0 p-3">
              <li class="flex-1 mr-2">
                <nuxt-link class="btn block" to="/">Home</nuxt-link>
              </li>
              <li class="flex-1 mr-2">
                <nuxt-link class="btn block" to="/blog">Blog</nuxt-link>
              </li>
              <li class="flex-1">
                <nuxt-link class="btn block" to="/projects">Projects</nuxt-link>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <div :class="menuClass">
      <div class="px-2 pt-5 mt-5 pb-3 space-y-1">
        <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
        <nuxt-link
          class="btn bg-gray-300 hover:bg-gray-700 text-white block px-3 py-2 rounded-md text-base font-medium"
          to="/"
          >Home</nuxt-link
        >
        <nuxt-link
          class="btn text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          to="/blog"
          >Blog</nuxt-link
        >

        <nuxt-link
          class="btn text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          to="/projects"
          >Projects</nuxt-link
        >
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data: function () {
    return {
      open: false,
    }
  },

  methods: {
    isOpen: function () {
      this.open = !this.open
    },
  },

  computed: {
    menuClass: function () {
      return this.open ? 'sm:hidden' : 'hidden sm:hidden'
    },
  },

  name: 'Header',
}
</script>

<style lang="postcss" scoped>
.nuxt-link-exact-active {
  @apply text-accent-100 bg-accent bg-opacity-20;
  &:hover {
    @apply text-white bg-accent-600;
  }
}
.light-mode {
  & .nuxt-link-exact-active {
    @apply text-accent-600;
    &:hover {
      @apply text-white;
    }
  }
}
</style>