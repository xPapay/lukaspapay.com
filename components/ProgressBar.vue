<template>
  <div>
    <div class="label">
      <slot />
    </div>
    <div class="bar">
      <div class="bar__level" :class="`bar__level--${progress}`" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    progress: {
      type: [String, Number],
      default: 0
    }
  }
}
</script>

<style scoped lang="scss">
$blue: #045cb8;

.label {
  font-size: 0.9rem;
  color: gray;
  font-family: 'Courier New', Courier, monospace;
}

.bar {
  display: inline-block;
  vertical-align: middle;
  width: 100%;
  height: 8px;
  background: lightgray;
  border-radius: 5px;
}

.bar__level {
  height: 100%;
  background: $blue;
  border-radius: inherit;
}

@for $i from 1 through 10 {
  .bar__level--#{$i} {
    width: $i * 10%;
  }
}
</style>
