<template>
  <div>
    <div class="posts">
      <NuxtLink
        :to="`/${post.id}`"
        v-for="post in paginatedPosts"
        :key="post.id"
        class="post">
        <img
          :src="`https://picsum.photos/280/280?random=${post.id}`"
          :alt="post.title"
          class="post__image" />
        <div class="post__content">
          <p class="post__text">{{ post.preview }}</p>
          <p class="post__read-more">Read more</p>
        </div>
      </NuxtLink>
    </div>
    <div class="pagination">
      <button
        v-if="currentPage > 1"
        @click="currentPage--"
        class="arrow-button">
        <ChevronLeft color="#000" />
      </button>
      <button
        v-for="page in displayedPages"
        :key="page"
        @click="currentPage = page"
        :class="{ active: currentPage === page }">
        {{ page }}
      </button>
      <button
        v-if="currentPage < totalPages"
        @click="currentPage++"
        class="arrow-button">
        <ChevronRight color="#000" />
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ChevronLeft, ChevronRight } from "lucide-vue-next";
import { computed, ref } from "vue";
interface Post {
  id: string;
  createdAt: string;
  title: string;
  preview: string;
  image: string;
  description: string;
}

const { data: posts, error } = await useFetch<Post[]>(
  "https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/"
);

if (error.value) {
  console.error("Error fetching posts:", error.value);
}

const currentPage = ref(1);
const postsPerPage = 8;

const totalPages = computed(() => {
  return Math.ceil((posts.value?.length || 0) / postsPerPage);
});

const paginatedPosts = computed(() => {
  if (!posts.value) return [];
  const startIndex = (currentPage.value - 1) * postsPerPage;
  const endIndex = startIndex + postsPerPage;
  return posts.value.slice(startIndex, endIndex);
});

const displayedPages = computed(() => {
  const start = Math.max(1, currentPage.value - 2);
  const end = Math.min(totalPages.value, start + 4);
  return Array.from({ length: end - start + 1 }, (_, i) => start + i);
});
</script>

<style lang="scss" scoped>
.posts {
  margin: 60px 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  row-gap: 44px;
  column-gap: 32px;
}

.post {
  background-color: #fff;
  overflow: hidden;
  max-width: 280px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
  text-decoration: none;
  transition: all 0.3s ease;
  &:hover {
    transform: translateY(-20px);
    .post__read-more {
      opacity: 1;
    }
  }

  &__image {
    width: 100%;
    height: 280px;
    object-fit: cover;
  }

  &__text {
    font-size: 20px;
    font-weight: 400;
    line-height: 1.2;
    color: $color-grey-1;
  }

  &__read-more {
    display: inline-block;
    opacity: 0;
    color: $color-purple-light;
    font-size: 20px;
    font-weight: 400;
    line-height: 1.2;
    text-decoration: none;
    margin-top: 12px;
    transition: all 0.3s ease;
  }
}

.pagination {
  display: flex;
  justify-content: flex-start;
  align-items: center;

  gap: 8px;

  button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 44px;
    height: 44px;
    border: currentColor;
    background-color: $color-grey-4;
    border-radius: 4px;
    cursor: pointer;

    &.active {
      background-color: $color-grey-1;
      color: white;
    }

    &:hover:not(.active) {
      background-color: #e8e8e8;
    }
  }

  .arrow-button {
    font-size: 20px;
    font-weight: bold;
    background-color: transparent;
    border: 1px solid $color-grey-4;
  }
}
</style>
