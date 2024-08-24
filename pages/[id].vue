<template>
  <div>
    <h1>Home Page with ID: {{ $route.params.id }}</h1>
    <NuxtLink to="/">Back to Home</NuxtLink>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
const id = route.params.id;
</script>
