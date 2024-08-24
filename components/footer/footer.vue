<template>
  <footer class="footer">
    <div class="footer__container">
      <FooterText />
      <FooterLinks />
    </div>
  </footer>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.footer {
  position: relative;
  overflow: hidden;
  width: 100%;
  height: 900px;
  background-color: $color-purple-light;
  padding-bottom: 30px;
  @media (max-width: 768px) {
    height: auto;
  }
  &__container {
    padding: 140px 112px 0;
    width: 100%;
    height: 100%;
    max-width: 1440px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    @media (max-width: 768px) {
      padding: 60px 20px 0;
    }
  }
}
</style>
