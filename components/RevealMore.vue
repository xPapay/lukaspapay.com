<template>
  <div>
    <div class="trigger" :class="{'trigger--revealed': reveal}" @click="reveal = !reveal">
      <slot name="trigger" />
    </div>
    <transition name="reveal">
      <div v-show="reveal">
        <slot />
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      reveal: false
    }
  }
}
</script>

<style scoped>
.trigger > * {
  display: inline-block;
}

.trigger::after {
  content: '';
  display: inline-block;
  margin-left: 10px;
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 0 10px 16px 10px;
  border-color: transparent transparent#045cb8 transparent;
  border-radius: 12px;
  cursor: pointer;
  transition: transform 0.2s;
}

.trigger--revealed::after {
  transform: rotateZ(180deg);
}

.reveal-enter,
.reveal-leave-to {
  /* max-height: 0px; */
  opacity: 0;
}

.reveal-enter-active,
.reveal-leave-active {
  /* max-height: 600px; */
  transition: all 0.5s;
}
</style>
