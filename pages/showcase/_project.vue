<template>
  <div class="row">
    <div class="col col-left">
      <div class="col__content">
        <div class="flex-column flex-space-between">
          <the-navigation />
          <div>
            <h1 class="col__headline">
              {{ project.headline }}
            </h1>
            <p class="col__subheadline">
              {{ project.subheadline }}
            </p>
            <div v-if="project.logo_path" class="text-center">
              <img class="logo" :src="project.logo_path" :alt="`${project.headline} project's logo`">
            </div>
          </div>
          <cta-button :to="project.url" class="self-center margin-vertical-l">
            Check it out!
          </cta-button>
          <dot-pagination :pages="projectPages" />
          <p v-if="project.stack" class="muted-text smaller-text">
            Built with: {{ project.stack }}
          </p>
        </div>
      </div>
    </div>
    <figure v-if="project.preview_path" class="col col-right figure">
      <img :src="project.preview_path" alt="Project preview image">
      <figcaption class="figcaption">
        {{ projectCaption }}
      </figcaption>
    </figure>
  </div>
  </div>
</template>

<script>
import TheNavigation from '@/components/TheNavigation'
import CtaButton from '@/components/CtaButton'
import DotPagination from '@/components/DotPagination.vue'
export default {
  components: {
    TheNavigation,
    CtaButton,
    DotPagination
  },
  validate({ params }) {
    return !!params.project
  },
  data() {
    return {
      projects: {
        wanderermap: {
          headline: 'Wanderermap',
          subheadline:
            'The most comprehensive map of public showers on internet helping travelers to arrive fresh to their destinations.',
          logo_path: '',
          preview_path: '/wanderermap.png',
          url: 'http://www.wanderermap.com',
          stack: 'Node.js (Express.js), MongoDB, React'
        },
        taskmanagement: {
          headline: 'Task management',
          subheadline:
            'This app was built for wood-crafting company to help with planning tasks',
          logo_path: '',
          preview_path: '/taskmanagement.png',
          url: 'http://demo.lukaspapay.com',
          stack: 'Laravel, MySQL, Vue.js'
        }
      }
    }
  },
  computed: {
    project() {
      return this.projects[this.$route.params.project]
    },
    projectCaption() {
      return `Screenshot of ${this.project.headline}`
    },
    projectPages() {
      return Object.keys(this.projects).map(projectName => ({
        name: 'showcase-project',
        params: { project: projectName }
      }))
    }
  }
}
</script>

<style lang="scss" scoped>
.figure {
  margin: 0;
  padding: 10px 0 20px 0;
  position: relative;
  filter: blur(4px);
}

.figure:after {
  content: '';
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #afe2e3;
  opacity: 0.2;
  transition: all 0.2s ease-in-out;
}

.figure:hover {
  filter: none;
}

.figure:hover:after {
  opacity: 0;
}

.figcaption {
  text-align: center;
  font-size: 0.8rem;
  color: #999;
  font-style: italic;
}
</style>
