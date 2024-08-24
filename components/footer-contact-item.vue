<template>
  <div class="footer__contacts-item">
    <p class="footer__contacts-title">{{ title }}</p>
    <p
      v-for="(contact, index) in contacts"
      :key="index"
      class="footer__contacts-text">
      {{ contact }}
    </p>
    <NuxtLink
      v-if="showButton && address"
      :to="googleMapsUrl"
      target="_blank"
      rel="noopener noreferrer"
      class="footer__contacts-button">
      <img
        src="~/assets/arrow.svg"
        alt="see location" />
    </NuxtLink>
  </div>
</template>

<script setup lang="ts">
interface Props {
  title: string;
  contacts: string[];
  showButton: boolean;
  address?: string;
}

const props = defineProps<Props>();

const googleMapsUrl = computed(() => {
  if (props.showButton && props.address) {
    const encodedAddress = encodeURIComponent(props.address);
    return `https://www.google.com/maps/search/?api=1&query=${encodedAddress}`;
  }
  return "";
});
</script>

<style scoped lang="scss">
.footer__contacts {
  &-title {
    margin-bottom: 12px;
  }
  &-text {
    font-size: 16px;
    font-weight: 400;
  }
  &-button {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: $color-grey-1;
    border: none;
    border-radius: 50%;
    width: 32px;
    height: 32px;
    cursor: pointer;
    margin-top: 8px;
    &:hover {
      background-color: $color-grey-2;
    }
    &:active {
      background-color: $color-grey-3;
    }
    &:focus {
      outline: transparent;
    }
    &:focus-visible {
      outline: 2px solid $color-grey-1;
      outline-offset: 2px;
    }
  }
}
</style>
