<template>
  <div class="error-page">
    <h1>{{ error.statusCode }}</h1>
    <p>{{ error.message }}</p>
    <NuxtLink
      to="/"
      class="home-link"
      >Go back to homepage</NuxtLink
    >
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  error: Object,
});

const error = props.error as { statusCode: number; message: string };
</script>

<style scoped lang="scss">
.error-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  text-align: center;

  h1 {
    font-size: 120px;
    margin-bottom: 20px;
  }

  p {
    font-size: 24px;
    margin-bottom: 30px;
  }

  .home-link {
    font-size: 18px;
    color: $color-purple-light;
    text-decoration: none;
    border: 2px solid $color-purple-light;
    padding: 10px 20px;
    border-radius: 5px;
    transition: all 0.3s ease;

    &:hover {
      background-color: $color-purple-light;
      color: $color-white;
    }
  }
}
</style>
