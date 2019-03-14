<template>
  <button v-if="!to" class="button">
    <slot />
  </button>
  <a v-else-if="isExternalLink" :href="to" class="button" target="_blank">
    <slot />
  </a>
  <nuxt-link v-else :to="to" class="button">
    <slot />
  </nuxt-link>
</template>

<script>
export default {
  props: {
    to: {
      type: [String, Object],
      default: null
    }
  },
  computed: {
    isExternalLink() {
      if (!this.to || typeof this.to === 'object') {
        return false
      }

      return !!this.to.match(/^(http|www)/i)
    }
  }
}
</script>


<style scoped lang="scss">
$background: #045cb8;

.button {
  text-align: center;
  font-size: 0.9rem;
  background-color: $background;
  color: white;
  border: none;
  padding: 18px;
  border-radius: 6px;
  cursor: pointer;
  text-transform: uppercase;
  box-shadow: 0 18px 18px -10px rgba(160, 160, 160, 0.5);
  transition: box-shadow 0.3s ease-in-out;
}

.button:hover {
  box-shadow: none;
}

.button:disabled {
  cursor: initial;
  box-shadow: none;
  background: lighten($background, 30%);
}
</style>
