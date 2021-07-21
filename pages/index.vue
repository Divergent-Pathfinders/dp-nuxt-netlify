<template>
  <div>
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
  },
  head () {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }]
    }
  }
}
</script>
