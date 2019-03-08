<template>
  <div class="row">
    <div class="col col-left">
      <div class="col__content">
        <div class="flex-column flex-space-between">
          <the-navigation />
          <div>
            <h1 class="col__headline">
              Hi. I'm webdeveloper Lukas
            </h1>
            <p class="col__subheadline">
              Sketching, styling, coding, testing, deploying... all the things I can do. I'm fullstack.
            </p>
            <div class="text-center">
              <img class="circle-picture" src="/avatar.png" alt="profile picture">
            </div>
          </div>
          <cta-button :to="{name: 'showcase-project', params: {project: 'wanderermap'}}" class="self-center margin-vertical-l">
            Look at My Showcase
          </cta-button>
        </div>
      </div>
    </div>
    <div class="col col-right">
      <img src="/hero.png" alt="hero image">
    </div>
  </div>
</template>

<script>
import TheNavigation from '@/components/TheNavigation'
import CtaButton from '@/components/CtaButton'

export default {
  components: {
    TheNavigation,
    CtaButton
  }
}
</script>
