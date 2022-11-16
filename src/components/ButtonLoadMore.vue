<script>
export default {
  name: 'ButtonLoadMore'
}
</script>

<template>
  <button class="btn-load-more">
    Load more
  </button>
</template>

<style lang="scss" scoped>
  @use '../style/partials/variables' as *;

  button {
    background-color: $primary-color;
    padding: 10px 60px;
    text-transform: uppercase;
    border: none;
    color: white;
    font-weight: 800;
    font-size: 12px;
  }
</style>