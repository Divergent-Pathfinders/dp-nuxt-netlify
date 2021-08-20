<template>
  <div>
    <h1>Projects</h1>
    <ul>
      <li v-for="project in projects" :key="project.title">
        <nuxt-link to="#">
          {{ project.title }}
        </nuxt-link>
      </li>
      <div align="center">
        <b-card
          v-for="project in projects"
          :key="project.title"
          style="max-width: 100rem;"
          align="left"
        >
          <nuxt-content :document="project" />
        </b-card>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const projects = await $content('projects', params.slug).fetch()

    return { projects }
  }
}
</script>
