<script setup lang="ts">
import TheHomeCategoryList from "@/components/TheHomeCategoryList.vue";
function bookImageUrl() {
  return new URL(`../assets/site-images/background.jpg`, import.meta.url).href;
}
</script>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  flex: 1;
  /* background-image: url(./site-images/background.jpg);
  background-repeat: round; */
}

.background-image {
  position: absolute;
  z-index: -1;
  width: 100%;
  height: -webkit-fill-available;
}

.welcome-text {
  width: fit-content;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: auto;
}

.welcome-title {
  color: var(--text-title);
  font-size: 64px;
  font-weight: 600;
  font-family: cursive;
}

.welcome-sub-header-cntr {
  display: flex;
  width: 100%;
  justify-content: space-between;
  gap: 6rem;
}

.welcome-sub-hrd {
  font-size: 24px;
  color: var(--text-black);
  font-weight: 600;
}

.category-images {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.welcome-cta-cntr {
}

.welcome-cta {
  padding: 16px;
  background: var(--secondary-background-color);
  border-radius: 4px;
  color: #fff;
  font-weight: 600;
  font-size: 24px;
  cursor: pointer;
}

.welcome-cta-link {
  text-decoration: none;
  color: var(--text-white) !important;
}

.category-images {
  flex: 1;
  padding: 50px;
}
</style>
<template>
  <img :src="bookImageUrl()" class="background-image" />
  <div class="home-page">
    <section class="welcome-text flow-content container">
      <section class="welcome-title">Welcome to Book Durbar</section>
      <section class="welcome-sub-header-cntr">
        <section class="welcome-sub-hrd">
          <div class="welcome-sub-title">
            Our durbar has variety options to choose from...
          </div>
          <div class="welcome-sub-title">Find your next best book today !</div>
        </section>
        <section class="welcome-cta-cntr">
          <div class="welcome-cta">
            <router-link :to="'/category/Classics'" class="welcome-cta-link">
              SHOP NOW
            </router-link>
          </div>
        </section>
      </section>
    </section>
    <section class="category-images container">
      <the-home-category-list></the-home-category-list>
    </section>
  </div>
</template>
