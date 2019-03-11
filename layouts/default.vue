<template>
  <div class="page">
    <nuxt />
  </div>
</template>

<script>
export default {
  head() {
    return {
      meta: [
        {
          property: 'og:url',
          content: process.env.BASE_URL + this.$route.path
        }
      ]
    }
  }
}
</script>
