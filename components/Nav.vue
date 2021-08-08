<template>
  <nav class="container px-6 py-4 mx-auto md:flex md:justify-between md:items-center">
    <div class="flex items-center justify-between">
      <nuxt-link
        class="
          text-xl
          font-bold
          text-white
          transition-colors
          duration-300
          transform
          md:text-2xl
          hover:text-indigo-400
        "
        to="/"
      >
        WebHex
      </nuxt-link>

      <!-- Mobile menu button -->
      <div class="flex md:hidden" @click="isOpen = !isOpen">
        <button
          type="button"
          class="text-gray-200 hover:text-gray-400 focus:outline-none focus:text-gray-400"
          aria-label="toggle menu"
        >
          <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
            <path
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
            ></path>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
    <div
      :class="isOpen ? 'flex' : 'hidden'"
      class="
        flex-col
        mt-2
        space-y-4
        md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0
      "
    >
      <nuxt-link
        class="
          text-sm
          font-medium
          text-gray-200
          transition-colors
          duration-300
          transform
          hover:text-indigo-400
        "
        to="/"
      >
        Home
      </nuxt-link>
      <nuxt-link
        class="
          text-sm
          font-medium
          text-gray-200
          transition-colors
          duration-300
          transform
          hover:text-indigo-400
        "
        to="/blog"
        >Blog</nuxt-link
      >
      <nuxt-link
        class="
          text-sm
          font-medium
          text-gray-200
          transition-colors
          duration-300
          transform
          hover:text-indigo-400
        "
        to="/about"
      >
        About
      </nuxt-link>
    </div>
  </nav>
</template>

<script lang="ts">
export default {
  data() {
    const isOpen = false
    return {
      isOpen,
    }
  },
}
</script>
