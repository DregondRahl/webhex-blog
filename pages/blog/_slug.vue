<template>
  <div>
    <Header />
    <div class="mt-6 mb-6">
      <div class="max-w-4xl px-10 py-6 mx-auto bg-white rounded-lg shadow-sm">
        <div class="flex items-center justify-between">
          <span class="font-light text-gray-600">{{ article.updatedAt }}</span>
        </div>
        <div class="mt-2">
          <nuxt-link
            :to="`blog/${article.slug}`"
            class="text-2xl font-bold text-gray-700 hover:underline"
          >
            {{ article.title }}
          </nuxt-link> by {{ article.author }}
          <p class="mt-2 text-gray-600">
            <nuxt-content :document="article"/>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  async asyncData({ $content, params }: any) {
    const article = await $content('blog', params.slug).fetch()

    return {
      article,
    }
  },
}
</script>
