<script setup lang="ts">
import { inject } from "vue";
import type { CategoryItem } from "@/types";
const categoryList = inject("categoryList") as CategoryItem[];
</script>

<style scoped>
.category-buttons {
  display: flex;
  flex-direction: row;
  background-color: #000;
  text-align: center;
}

.button.category-button.router-link-active {
  background-color: var(--secondary-background-color);
  border: 1px solid #fff;
}

.button.category-button {
  background-color: #000;
}

.button.category-button:hover,
.button.category-button:active {
  background-color: var(--secondary-background-color);
}
</style>

<template>
  <nav class="category-nav">
    <ul class="category-buttons">
      <li v-for="category in categoryList" :key="category.categoryId">
        <router-link :to="'/category/' + category.name" class="button category-button">
          {{ category.name }}
        </router-link>
      </li>
    </ul>
  </nav>
</template>
