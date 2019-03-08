<template>
  <div>
    <div class="row">
      <div class="col col-left">
        <div class="col__content">
          <div class="flex-column flex-space-between">
            <the-navigation />
            <div>
              <h1 class="col__headline">
                Hire me
              </h1>
              <p class="col__subheadline">
                Do you need landing page, blog, single page app or even web app working offline? I have it fully covered both front and back end.
              </p>
            </div>
            <cta-button :to="{name: 'contact'}" class="self-center margin-vertical-l">
              Hire me!
            </cta-button>
          </div>
        </div>
      </div>
      <div class="col col-right">
        <img src="/hire-me.png" alt="hero image">
      </div>
    </div>
    <div class="row">
      <div class="col col-left">
        <div class="col__content">
          <reveal-more>
            <template v-slot:trigger>
              <h2>My skills</h2>
            </template>
            <ul class="flex flex-wrap skills-list flex-space-between">
              <li>
                <progress-bar progress="9">
                  PHP (Laravel)
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="8">
                  Node.js (express.js)
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="9">
                  MySQL
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="7">
                  MongoDB
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="9">
                  Vue.js
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="7">
                  React
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="7">
                  PHPUnit
                </progress-bar>
              </li>
              <li>
                <progress-bar progress="7">
                  Ava
                </progress-bar>
              </li>
            </ul>
          </reveal-more>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TheNavigation from '@/components/TheNavigation'
import CtaButton from '@/components/CtaButton'
import ProgressBar from '@/components/ProgressBar.vue'
import RevealMore from '@/components/RevealMore.vue'

export default {
  components: {
    TheNavigation,
    CtaButton,
    ProgressBar,
    RevealMore
  }
}
</script>

<style lang="scss" scoped>
.skills-list li {
  width: 200px;
}
</style>
