<script setup lang="ts">
import { inject } from "vue";
import type { CategoryItem } from "@/types";
const categoryList = inject("categoryList") as CategoryItem[];
</script>

<style scoped>
.header-dropdown {
  position: relative;
  margin: auto 0;
}

.categories-button {

  text-align: center;
  background: #fff !important;
  color: #000 !important;
  border: 1px solid black;
  border-radius: 8px;
}

.header-dropdown ul {
  display: none;
  background-color: white;
  color: black;
  border-radius: 4px;
}

.header-dropdown li {
  padding: 0.25em 0.5em;
}

.header-dropdown a {
  color: black;
  text-decoration: none;
  display: block;
  width: 100%;
}

.header-dropdown li:hover {
  background: #cbd5e1;

}

.header-dropdown:hover ul {
  position: absolute;
  z-index: 1;
  display: block;
  min-width: 8em;
  cursor: pointer;
}
</style>

<template>
  <div class="header-dropdown">
    <button class="button categories-button">
    Categories
    <i class="fas fa-chevron-down"></i>
    </button>
    <ul>
      <li v-for="category in categoryList" :key="category.categoryId">
        <router-link :to="'/category/' + category.name">
          {{ category.name }}
        </router-link>
      </li>
    </ul>
  </div>
</template>
