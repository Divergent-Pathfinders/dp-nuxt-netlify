<template>
  <div>
    <h1>
      {{ all.sitetitle }}
    </h1>
    <nuxt-content :document="page" />
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
