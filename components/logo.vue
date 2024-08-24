<template>
  <div>
    <NuxtLink
      to="/"
      class="logo-link"
      aria-label="Home">
      <img
        class="logo"
        src="~/assets/logo.png"
        alt="Company Logo" />
    </NuxtLink>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.logo-link {
  display: inline-block;
  transition: opacity 0.3s ease;
  border-radius: 4px;

  &:hover {
    opacity: 0.7;
  }
  &:focus {
    outline: none;
  }
  &:focus-visible {
    outline: 2px solid $color-grey-1;
    outline-offset: 2px;
  }
}
.logo {
  width: 84px;
  height: 25px;
  object-fit: contain;
}
</style>
