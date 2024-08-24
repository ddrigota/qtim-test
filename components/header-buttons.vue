<template>
  <div class="header-buttons">
    <button
      class="header-buttons__lang"
      type="button"
      aria-label="Change language">
      <img
        class="header-buttons__lang-icon"
        src="~/assets/uk.png"
        alt=""
        aria-hidden="true" />
    </button>
    <NuxtLink
      class="header-buttons__link"
      type="button"
      to="https://qtim.pro/">
      Let's Work
    </NuxtLink>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.header-buttons {
  display: flex;
  align-items: center;
  gap: 16px;
  &__lang {
    display: flex;
    align-items: center;
    border-radius: 50%;
    padding: 12px;
    border: 2px solid rgb(0 0 0 / 0.1);
    background-color: transparent;
    transition: background-color 0.3s ease;
    cursor: pointer;
    &:hover {
      background-color: $color-grey-4;
    }
    &:active {
      background-color: $color-grey-3;
    }
    &:focus {
      outline: none;
    }
    &:focus-visible {
      outline: 2px solid $color-grey-1;
      outline-offset: 2px;
    }
  }
  &__lang-icon {
    width: 24px;
    height: 24px;
    object-fit: contain;
  }
  &__link {
    display: flex;
    text-decoration: none;
    align-items: center;
    padding: 11px 32px;
    border-radius: 999px;
    border: none;
    background-color: $color-grey-1;
    color: $color-white;
    font-size: 20px;
    font-weight: 400;
    cursor: pointer;
    transition: background-color 0.3s ease;
    &:hover {
      background-color: $color-grey-2;
    }
    &:active {
      background-color: $color-grey-3;
    }
  }
}
</style>
