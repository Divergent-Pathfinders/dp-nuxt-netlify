<template>
  <div>
    <div>
      <b-jumbotron :header="page.headline" :lead="page.strapline">
        <p>{{ page.explainer }}</p>
      </b-jumbotron>
    </div>
    <div align="center">
      <b-card
        style="max-width: 100rem;"
        align="left"
      >
        <nuxt-content :document="page" />
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const page = await $content('pages/index')
      .fetch()
    const all = await $content('all')
      .fetch()
    return {
      page,
      all
    }
  },
  head () {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }]
    }
  }
}
</script>
