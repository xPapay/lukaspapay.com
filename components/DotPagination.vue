<template>
  <div class="pagination">
    <nuxt-link v-for="(page, index) in pages" :key="index" :to="page" class="pagination__link" />
  </div>
</template>

<script>
export default {
  props: {
    pages: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.pagination {
  text-align: center;
}

.pagination__link {
  display: inline-block;
  width: 12px;
  height: 12px;
  background-color: gray;
  margin: 20px 8px;
  border-radius: 50%;
}

.pagination__link.nuxt-link-active {
  background-color: #045cb8;
}
</style>
