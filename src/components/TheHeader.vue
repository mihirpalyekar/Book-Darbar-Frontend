<script setup lang="ts">
import TheHeaderDropdown from "@/components/TheHeaderDropdown.vue";
import TheHeaderSearchBar from "@/components/TheHeaderSearchBar.vue";
</script>

<style scoped>
header {
  display: flex;
  flex-direction: column;
  background: var(--secondary-background-color);
}

.text-logo {
  font-family: var(--title-font-family);
}

.header-cntr {
  padding: 0;
}

.header-container {
  display: flex;
  flex-direction: row;
  background: var(--secondary-background-color);
  padding: 20px 50px;
  width: 100%;
}

.bookstore-logo {
  display: flex;
  justify-content: space-between;
  min-width: 300px;
  padding-right: 20px;
  align-items: center;
  flex: auto;
}
.bookstore-logo > a {
  display: flex;
  text-decoration: none;
  align-items: center;
  gap: 12px;
}

.bookstore-logo > a > i {
  font-size: 48px;
  color: var(--text-white);
}

.text-logo {
  font-family: cursive;
  color: var(--text-white);
  font-size: 36px;
  font-weight: 600;
}

.header-dropdown-and-cart {
  display: flex;
  justify-content: space-between;
  min-width: 200px;
  flex: 3;
}

.fa-shopping-cart {
  position: relative;
}

.cart-count {
  position: absolute;
  right: -11px;
  top: -14px;
  color: black;
  font-size: 16px;
  background: #fff;
  padding: 4px;
  border: 1px solid black;
  border-radius: 50%;
}

.nav-bar-container {
  padding: 12px 50px;
  display: flex;
  gap: 24px;
  background: rgba(255, 255, 255);
}

.nav-bar-cta {
  padding: 8px 16px;
  background: var(--text-primary);
  border-radius: 4px;
  color: #fff;
  font-weight: 500;
  font-size: 16px;
  cursor: pointer;
}

.hdr-button {
  background: none;
  border: none;
  font-size: 32px;
  padding: 0;
}

@media (max-width: 600px) {
  header {
    flex-direction: column;
  }
}

@media (max-width: 600px) {
  header {
    flex-direction: column;
  }
}
</style>

<template>
  <header class="">
    <section class="header-container">
      <section class="bookstore-logo">
        <router-link to="/">
          <i class="fa-solid fa-landmark-dome"></i>
          <h1 class="text-logo">Book Durbar</h1>
        </router-link>
      </section>
      <TheHeaderSearchBar></TheHeaderSearchBar>
      <section class="header-dropdown-and-cart">
        <the-header-dropdown></the-header-dropdown>
        <button class="button hdr-button"><i class="fas fa-heart"></i></button>
        <button class="button hdr-button">
          <i class="fas fa-shopping-cart"><span class="cart-count">3</span></i>
        </button>
        <button class="button hdr-button"><i class="fas fa-user"></i></button>
      </section>
    </section>
    <section></section>
  </header>
</template>
