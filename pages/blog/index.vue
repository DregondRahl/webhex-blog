<template>
  <div>
    <Header />
    <div v-for="article in articles" :key="article.slug" class="mt-6 mb-6">
      <div class="max-w-4xl px-10 py-6 mx-auto bg-white rounded-lg shadow-sm">
        <div class="flex items-center justify-between">
          <span class="font-light text-gray-600">{{ formatDate(article.updatedAt) }}</span>
        </div>
        <div class="mt-2">
          <nuxt-link
            :to="`blog/${article.slug}`"
            class="text-2xl font-bold text-gray-700 hover:underline"
          >
            {{ article.title }}
          </nuxt-link>
          <p class="mt-2 text-gray-600">
            {{ article.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  async asyncData({ $content }: any) {
    const articles = await $content('blog').fetch()

    return {
      articles,
    }
  },
  methods: {
    formatDate(date: any){
      return new Date(date).toLocaleDateString('en', {
        year: 'numeric',
        month:'long',
        day: 'numeric'
      })
    }
  },
}
</script>
