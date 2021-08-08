<template>
  <div>
    <Header />
    <section class="bg-white">
      <div class="max-w-5xl px-6 py-16 mx-auto">
        <div class="items-center md:flex md:space-x-6">
          <div class="md:w-1/2">
            <h3 class="text-2xl font-semibold text-gray-800">
              {{ about.title }}
            </h3>
            <p class="max-w-md mt-4 text-gray-600">
              <nuxt-content :document="about" />
            </p>
          </div>
          <div class="mt-8 md:mt-0 md:w-1/2">
            <div class="flex items-center justify-center">
              <div class="max-w-md">
                <img
                  class="object-cover object-center w-full rounded-md shadow"
                  style="height: 800px"
                  src="https://images.unsplash.com/photo-1616874535244-73aea5daadb9?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
export default {
  async asyncData({ $content }: any) {
    const about = await $content('about').fetch()

    return {
      about,
    }
  },
}
</script>
