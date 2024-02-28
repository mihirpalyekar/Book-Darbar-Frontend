<script setup lang="ts">
import { defineProps } from "vue";
import type { BookItem } from "@/types";
const props = defineProps<{
  book: BookItem;
}>();
const bookImageFileName = function (book: BookItem): string {
  let name = book.imgUrl
  name = name.replace(/ /g, "-");
  name = name.replace(/'/g, "");
  return `${name}`;
};

function bookImageUrl(imageFileName:string) {
  console.log(new URL(`../assets/book-images/${imageFileName}`,import.meta.url).href,imageFileName)
  return new URL(`../assets/book-images/${imageFileName}`,import.meta.url).href;
};
</script>
<style scoped>
.book-box {
  display: flex;
  flex-direction: column;
  border: 1px solid #CBD5E1;
  border-radius: 8px;
}

.book-info-cntr{
  display: flex;
  justify-content: space-between;
}
.book-info {
  padding: 12px 8px;
  max-width: 250px;
}

.book-title {
  font-weight: bold;
}

.book-author {
  font-style: italic;
}

.book-title {
  font-weight: bold;
  color: #2E2D42;
  font-size: 18px;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.book-author {
  font-style: italic;
  color: #4F4F4F;
  text-decoration: underline;
  font-weight: 600;
}

.book-price{
  background: #EBEBEC;
  border-radius: 50%;
  min-width: 48px;
  min-height: 48px;
  max-width: 48px;
  max-height: 48px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 14px;
  font-weight: 600;
  color: #000;
}

.add-to-cart {
  width: 100%;
  color: #fff;
  border: none;
  background: #2B5582;
  padding: 8px 0;
  margin-top: 8px;
  border-radius: 4px;
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
}

.read-now-cta:hover{
  background-color: #fff;
}

.fa-book {
  color: var(--secondary-background-color);
  font-size: 24px;
}

</style>

<template>
  <li class="book-box">
    <div class="book-image">
      <a style="position:relative" href="#">
        <img
          :src="bookImageUrl(bookImageFileName(props.book))"
          :alt="book.title"
        />
        <button v-if="props.book.isPublic" class="button read-now-cta"><i class="fas fa-book"></i></button>
      </a>
    </div>
    <div class="book-info">
      <div class="book-info-cntr">
        <div class="book-details">
          <div class="book-title">{{ book.title }}</div>
          <div class="book-author">{{ book.author }}</div>
        </div>
        <div class="book-price">${{ book.price }}</div>
      </div>
      <button class="button add-to-cart">Add to Cart</button>
    </div>
  </li>
</template>
