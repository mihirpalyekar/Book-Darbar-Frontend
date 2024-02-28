<script setup lang="ts"></script>

<style scoped>
.title-and-search-bar {
  flex: 4;
}

.search-container{
  border: 3px solid #fff;
  width: fit-content;
  border-radius: 4px;
}

.search-form {
  display: flex;
}
.search-bar {
  padding: 0.8rem;
  border: none;
  background: var(--secondary-background-color);
  border: none;
  border-radius: 4px;
  color: var(--text-white);
  width: 25vw;
}

.search-bar::placeholder {
  color: var(--text-white);
  font-size: 24px;
}

.search-button {
  background: var(--secondary-background-color);
  border: none;
  border-left: 1px solid #fff;
  padding: 12px;
  font-size: 24px;
}
</style>

<template>
  <section class="title-and-search-bar">
    <div class="search-container">
      <form class="search-form" action="category.html">
        <input type="text" class="search-bar" placeholder="Search book"/>
        <i class="fas fa-search button search-button"><input type="hidden" class="" value="" /></i>
      </form>
    </div>
  </section>
</template>
