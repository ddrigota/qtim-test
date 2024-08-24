<template>
  <div class="footer__contacts">
    <FooterContactItem
      title="For all questions"
      :contacts="['+7 (920) 278—00—68', 'qtim@agency.com']"
      :show-button="false" />
    <FooterContactItem
      title="Office in Russia"
      :contacts="['139 Ruben Station Lake Drew, NM 52678']"
      :show-button="true"
      address="139 Ruben Station Lake Drew, NM 52678" />
    <FooterContactItem
      title="Office in Dubai"
      :contacts="['139 Ruben Station Lake Drew, NM 52678']"
      :show-button="true"
      address="139 Ruben Station Lake Drew, NM 52678" />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.footer__contacts {
  padding-top: 12px;
  line-height: 100%;
  max-width: 152px;
  display: flex;
  flex-direction: column;
  gap: 36px;
  font-size: 16px;
  font-weight: 400;
  line-height: 19.2px;
}
</style>
