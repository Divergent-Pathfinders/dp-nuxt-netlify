<template>
  <article>
    <p>
      <nuxt-content :document="page" />
    </p>
  </article>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const page = await $content('hello').fetch()
    return {
      page
    }
  }
}
</script>

<script>
export default {
  head () {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }]
    }
  }
}
</script>
