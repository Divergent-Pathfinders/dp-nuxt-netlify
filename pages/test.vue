<template>
  <div>
    <h1>{{ page.title }}</h1>
    <p>{{ page.description }}</p>
    <nuxt-content :document="page" />
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const page = await $content('hello')
      .fetch()
    return {
      page
    }
  }
}
</script>
