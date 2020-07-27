<template>
  <main>
    <div v-for="article in articles" :key="article.slug" class="cards">
      <nuxt-link :to="article.slug">
        <div class="card convex">
          {{ article.title }}
        </div>
      </nuxt-link>
    </div>
  </main>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const articles = await $content('articles').fetch()
    return { articles }
  }
}
</script>

<style>
</style>
