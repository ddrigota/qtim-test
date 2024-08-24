<template>
  <footer class="footer">
    <div class="footer__container">
      <FooterText />
      <div class="footer__links"></div>
    </div>
  </footer>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.footer {
  width: 100%;
  height: 900px;
  background-color: $color-purple-light;
  &__container {
    padding: 140px 112px 0;
    width: 100%;
    height: 100%;
    max-width: 1440px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
}
</style>
