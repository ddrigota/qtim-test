<template>
  <header class="header">
    <Logo />
    <nav class="header-nav">
      <HeaderLinks />
      <HeaderButtons />
    </nav>
  </header>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 40px;
  height: 121px;
  max-width: 1440px;
  margin: 0 auto;
}
.header-nav {
  display: flex;
  align-items: center;
  gap: 91px;
}
</style>
