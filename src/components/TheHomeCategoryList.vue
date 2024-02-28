<script setup lang="ts">
import { inject } from "vue";
import type { CategoryItem, BookItem } from "@/types";
const categoryList = inject("categoryList") as CategoryItem[];
const latestArrivalsList = inject("latestArrivalsList") as BookItem[]
const categoryImageFileName = function (category: BookItem): string {
  let name = category.imgUrl.toLowerCase();
  name = name.replace(/ /g, "-");
  name = name.replace(/'/g, "");
  return `${name}`;
};
function bookImageUrl(imageFileName:string) {
  return new URL(`../assets/book-images/${imageFileName}`,import.meta.url).href;
};
</script>

<style scoped>
ul {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;

  gap: 1em;
}

li {
  text-align: center;
  cursor: pointer;
}

li div {
  margin-bottom: -2em;
  padding: 0.5em 0;
  background: rgba(0, 0, 0, 0.5); /* last # is percent opacity */
  color: white;
  transform: translateY(-2.25em);
}

.category-images-title {
  font-size: 40px;
  color: var(--text-black);
  font-weight: 600;
}

.img-cont-box {
  position: relative;
}

.read-now-cta {
  position: absolute;
  top: 10px;
  right: 10px;
  width: 48px;
  background: #fff;
  height: 48px;
  border-radius: 50%;
  border: none;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var( --text-primary);
  font-size: 24px;
}
.latest-book-img {
  width: 180px;
  height: 180px;
}
</style>

<template>
  <div class="category-images-title">Latest arrivals</div>
  <div class="category-image-items">
    <ul>
      <li v-for="category in latestArrivalsList" :key="category.bookId">
        <router-link
          :to="'/category/' + category.bookCategory"
          class="img-cont-box"
        >
          <img
            :src="bookImageUrl(categoryImageFileName(category))"
            :alt="category.title + ' category'"
            class="latest-book-img"
          />
          <button v-if="category.isPublic" class="button read-now-cta"><i class="fas fa-book"></i></button>
          <div>{{ category.title }}</div>
        </router-link>
      </li>
    </ul>
  </div>
</template>
