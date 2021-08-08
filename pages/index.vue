<template>
  <div>
    <Landing />

    <section class="bg-white">
      <div class="max-w-5xl px-6 py-16 mx-auto">
        <div class="items-center md:flex md:space-x-6">
          <div class="md:w-1/2">
            <h3 class="text-2xl font-semibold text-gray-800">
              {{ featured.title }}
            </h3>
            <p class="max-w-md mt-4 text-gray-600">
              <nuxt-content :document="featured" />
            </p>
          </div>
          <div class="mt-8 md:mt-0 md:w-1/2">
            <div class="flex items-center justify-center">
              <div class="max-w-md">
                <img
                  class="object-cover object-center w-full rounded-md shadow"
                  style="height: 500px"
                  src="https://images.unsplash.com/photo-1618346136472-090de27fe8b4?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=673&q=80"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-white">
      <div class="max-w-5xl px-6 py-16 mx-auto">
        <div class="items-center md:flex md:space-x-6">
          <div class="md:w-1/2">
            <div class="flex items-center justify-center">
              <div class="max-w-md">
                <img
                  class="object-cover object-center w-full rounded-md shadow"
                  style="height: 500px"
                  src="https://images.unsplash.com/photo-1616874535244-73aea5daadb9?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80"
                />
              </div>
            </div>
          </div>
          <div class="mt-8 md:mt-0 md:w-1/2">
            <h3 class="text-2xl font-semibold text-gray-800">{{ popular.title }}</h3>
            <p class="max-w-md mt-4 text-gray-600">
              <nuxt-content :document="popular" />
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
export default {
  async asyncData({ $content }: any) {
    const popular = await $content('popular').fetch()
    const featured = await $content('featured').fetch()
    return {
      popular,
      featured,
    }
  },
}
</script>
