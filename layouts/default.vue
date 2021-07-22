<template>
  <div>
    <header>
      <div>
        <b-navbar toggleable="lg" type="dark" variant="primary">
          <b-navbar-brand to="/">
            <img src="icon.png" class="d-inline-block align-mid" :alt="all.strapline" width="80px">
            {{ all.sitetitle }}
          </b-navbar-brand>
          <b-navbar-toggle target="nav-collapse" />
          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav class="ml-auto">
              <b-nav-item to="/about/">
                About
              </b-nav-item>
              <b-nav-item to="/posts/">
                Posts
              </b-nav-item>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
        <slot />
      </div>
    </header>
    <Nuxt />
    <TheFooter />
  </div>
</template>

<script>
export default {
  data () {
    return {
      all: []
    }
  },
  async fetch () {
    this.all = await this.$content('all').fetch()
  }
}
</script>
