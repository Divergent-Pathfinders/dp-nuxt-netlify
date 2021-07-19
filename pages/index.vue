<template>
  <div>
    <p>
      {{ all }}
    </p>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const all = await $content('pages/all').fetch()

    return {
      all
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
