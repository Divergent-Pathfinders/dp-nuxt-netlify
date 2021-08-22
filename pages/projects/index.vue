<template>
  <div style="max-width: 100rem;">
    <h1>Projects</h1>
    <div align="center">
      <b-card-group>
        <b-card
          v-for="project in projects"
          :key="project.title"
          :title="project.title"

          align="left"
        >
          <nuxt-content :document="project" />
          <nuxt-link :to="`projects/${project.slug}`">
            Find out more about {{ project.title }}
          </nuxt-link>
        </b-card>
      </b-card-group>
    </div>
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
