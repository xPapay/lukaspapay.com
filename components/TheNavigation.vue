<template>
  <nav class="navigation">
    <nuxt-link key="index" :to="{name: 'index'}">
      Home
    </nuxt-link>
    <nuxt-link key="hire-me" :to="{name: 'hire-me'}">
      Hire Me
    </nuxt-link>
    <nuxt-link key="showcase" :to="{name: 'showcase-project', params: {project: 'wanderermap'}}">
      Showcase
    </nuxt-link>
    <nuxt-link key="contact" :to="{name: 'contact'}">
      Contact
    </nuxt-link>
  </nav>
</template>

<script>
export default {}
</script>

<style scoped>
.navigation {
  display: flex;
  justify-content: space-between;
}

.navigation > .nuxt-link-exact-active {
  box-shadow: 0 6px 0 -4px black;
}
</style>
