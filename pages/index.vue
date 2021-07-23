<template>
  <div>
    <div style="padding:2rem;" align="center">
      <b-jumbotron
        :header="page.headline"
        :lead="page.strapline"
        bg-variant="secondary"
        text-variant="white"
        border-variant="dark"
        style="max-width: 100rem;"
        class="shadow"
        align="left"
      >
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
