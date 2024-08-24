<template>
  <div aria-label="Main navigation">
    <ul class="header-links">
      <li
        v-for="link in links"
        :key="link.text"
        class="header-links__item">
        <NuxtLink
          :to="link.to"
          class="header-links__link">
          {{ link.text }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
const links = [
  { text: "Works", to: "#" },
  { text: "About", to: "#" },
];
</script>

<style scoped lang="scss">
.header-links {
  display: flex;
  align-items: center;
  gap: 58px;
  list-style: none;
  padding: 0;
  margin: 0;
  font-size: 20px;
  font-weight: 400;
  line-height: 1;
  color: $color-grey-1;

  &__link {
    text-decoration: none;
    color: inherit;
    border-radius: 4px;
    transition: opacity 0.3s ease;

    &:hover,
    &:focus {
      opacity: 0.7;
    }
    &:focus-visible {
      outline: 2px solid $color-grey-1;
      outline-offset: 2px;
    }
  }
}
</style>
