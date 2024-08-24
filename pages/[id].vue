<template>
  <section>
    <div
      v-if="post"
      class="post">
      <h1 class="post__title">{{ post.title }}</h1>
      <img
        class="post__image"
        :src="`https://picsum.photos/1280/700?random=${post.id}`"
        :alt="post.title" />
      <div class="post__text">
        <p class="post__about">About</p>
        <p class="post__description">{{ post.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
type TPost = {
  id: string;
  createdAt: string;
  title: string;
  preview: string;
  description: string;
  image: string;
};
const route = useRoute();
const { data: post, error } = await useFetch<TPost>(
  `https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/${route.params.id}`
);

// If you want to handle 404 errors specifically
if (error.value?.statusCode === 404) {
  throw createError({ statusCode: 404, statusMessage: "Post not found" });
}
</script>

<style scoped lang="scss">
.post {
  padding: 120px 112px 80px;
  display: flex;
  flex-direction: column;
  gap: 80px;
  &__title {
    font-size: 84px;
    font-weight: 400;
    line-height: 100%;
  }
  &__text {
    display: flex;
    flex-direction: column;
    gap: 32px;
  }
  &__about {
    font-size: 16px;
    font-weight: 400;
    line-height: 100%;
  }
  &__description {
    font-size: 36px;
    font-weight: 400;
    line-height: 120%;
  }
  &__image {
    width: 100%;
    height: 700px;
    object-fit: cover;
  }
}
</style>
