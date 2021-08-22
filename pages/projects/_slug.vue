<template>
  <article>
    <h1> {{ project.title }} </h1>
    <nuxt-content :document="project" />
  </article>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const project = await $content('projects', params.slug).fetch()

    return { project }
  }
}
</script>
