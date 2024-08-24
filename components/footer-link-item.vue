<template>
  <NuxtLink
    :to="link"
    class="footer-link-item"
    target="_blank"
    rel="noopener noreferrer">
    {{ text }}
  </NuxtLink>
</template>

<script setup lang="ts">
interface Props {
  text: string;
  link: string;
}

defineProps<Props>();
</script>

<style scoped lang="scss">
.footer-link-item {
  font-size: 16px;
  font-weight: 400;
  line-height: 19.2px;
  color: $color-grey-1;
  transition: opacity 0.3s ease;
  text-underline-offset: 5px;
  text-decoration-thickness: 1px;
  border-radius: 4px;

  &:hover,
  &:focus {
    opacity: 0.7;
  }

  &:focus-visible {
    outline: 2px solid $color-grey-1;
    outline-offset: 2px;
  }
}
</style>
