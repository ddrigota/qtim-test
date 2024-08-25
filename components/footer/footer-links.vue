<template>
  <div class="footer__links">
    <div class="footer__links-left">
      <FooterLinkItem
        v-for="link in linksLeft"
        :key="link.text"
        :text="link.text"
        :link="link.link" />
    </div>
    <FooterMainButton />
    <div class="footer__links-right">
      <FooterLinkItem
        v-for="link in linksRight"
        :key="link.text"
        :text="link.text"
        :link="link.link" />
    </div>
  </div>
</template>

<script setup lang="ts">
const linksLeft = [
  { text: "Facebook", link: "https://www.facebook.com/" },
  { text: "Instagram", link: "https://www.instagram.com/" },
  { text: "Telegram", link: "https://www.telegram.com/" },
];
const linksRight = [
  { text: "Behance", link: "https://www.behance.net/" },
  { text: "Linkedin", link: "https://www.linkedin.com/" },
  { text: "Privacy Policy", link: "#" },
];
</script>

<style scoped lang="scss">
.footer__links {
  display: flex;
  justify-content: space-between;
  @media (max-width: 768px) {
    justify-content: space-between;
  }
  &-left,
  &-right {
    display: flex;
    gap: 32px;
    @media (max-width: 768px) {
      flex-direction: column;
      justify-content: flex-start;
    }
  }
}
</style>
