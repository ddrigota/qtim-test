<template>
  <div class="footer__text">
    <p class="footer__text-title">Is there a project?</p>
    <div class="footer__text-grid">
      <p class="footer__text-subtitle">Let's work together</p>
      <FooterContacts />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.footer {
  &__text-grid {
    margin-top: 56px;
    display: grid;
    grid-template-columns: 2fr 1fr;

    @media (max-width: 768px) {
      grid-template-columns: 1fr;
      gap: 40px;
    }
  }
  &__text-subtitle {
    font-size: 112px;
    font-weight: 400;
    text-decoration: underline;
    line-height: 100%;
    text-underline-offset: 10px;
    text-decoration-thickness: 1px;
    text-decoration-skip-ink: all;

    @media (max-width: 768px) {
      font-size: 48px;
    }
  }
}
</style>
