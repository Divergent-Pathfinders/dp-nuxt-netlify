<template>
  <div>
    <h1>
      {{ all.sitetitle }}
    </h1>
    <nuxt-content :document="page1" />
  </div>
</template>

<script>
/* eslint-disable */
export default {
  async asyncData ({ $content }) {
    const page = await $content('pages/index-body-1')
      .fetch()
    return {
      page
    }
  },
    async asyncData ({ $content }) {
    const all = await $content('all')
      .fetch()
    return {
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
