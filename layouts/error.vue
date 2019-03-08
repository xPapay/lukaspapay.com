<template>
  <div v-if="error.statusCode === 404" class="not-found">
    <cta-button :to="{name: 'index'}" class="go-home">
      Go Home
    </cta-button>
  </div>
  <div v-else>
    <h1>Something went wrong</h1>
    <cta-button :to="{name: 'index'}" class="go-home">
      Go Home
    </cta-button>
  </div>
</template>

<script>
import CtaButton from '@/components/CtaButton.vue'
export default {
  components: {
    CtaButton
  },
  props: {
    error: {
      type: Object,
      default: null
    }
  }
}
</script>


<style scoped>
.not-found {
  background: url('/404.png') center no-repeat;
  background-size: cover;
  height: 600px;
  position: relative;
}

.go-home {
  position: absolute;
  bottom: 100px;
  left: 50%;
  transform: translateX(-50%);
}
</style>
