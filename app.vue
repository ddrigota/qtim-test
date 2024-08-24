<template>
  <div>
    <NuxtLayout>
      <div class="container">
        <Header />
        <NuxtPage />
      </div>
      <Footer />
    </NuxtLayout>
  </div>
</template>

<script setup></script>

<style scoped lang="scss">
.container {
  max-width: 1440px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
}
</style>
