<template>
  <section class="posts">
    <h1 class="posts__title">Articles</h1>
    <Posts />
  </section>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.posts {
  flex: 1;
  padding: 120px 112px;
  &__title {
    font-size: 84px;
    font-weight: 400;
    line-height: 100%;
  }
}
</style>
