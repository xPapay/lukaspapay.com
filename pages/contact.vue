<template>
  <div class="row">
    <div class="col col-left overflow-hidden">
      <div class="col__content">
        <the-navigation />
        <div class="flex flex-v-center relative">
          <transition name="getout">
            <div v-if="!submitted" key="1">
              <h1 class="col__headline">
                Let's work together
              </h1>
              <contact-form @submit="submitted = !submitted" />
            </div>
            <div v-else key="2">
              <h1>Thank you :)</h1>
            </div>
          </transition>
        </div>
      </div>
    </div>
    <div class="col col-right">
      <img src="/contact.png" alt="hero image">
    </div>
  </div>
</template>

<script>
import TheNavigation from '@/components/TheNavigation'
import ContactForm from '@/components/ContactForm.vue'

export default {
  components: {
    TheNavigation,
    ContactForm
  },
  data() {
    return {
      submitted: false
    }
  }
}
</script>

<style lang="scss" scoped>
.relative {
  position: relative;
}

.overflow-hidden {
  overflow: hidden;
}

.getout-leave-active {
  transform: translateX(-200%);
  position: absolute;
}

.getout-enter {
  transform: translateX(200%);
}

.getout-enter-active,
.getout-leave-active {
  transition: transform 0.5s cubic-bezier(0.34, 1.265, 0, 1.12);
}
</style>
