<script setup lang="ts"></script>

<style scoped>
footer {
  background: var(--primary-background-color);
  display: flex;
  gap: 1em;
  border-top: 1.5px solid var(--secondary-background-color);

}

.footer-cntr {
  padding: 24px 50px;
}

.copy-write-text {
  color: var(--text-gray);
  font-size: 12px;
  font-weight: 600;
}

.links,
.social-media-icons {
  display: flex;
  flex: 4;
  justify-content: space-around;
  color: var(--text-gray);
  cursor: pointer;

}
.social-media-icons {
  flex: 1;
  font-size: 20px;
  font-weight: 600;
}
.links > a {
  color: var(--text-gray);
  font-size: 16px;
  font-weight: 600;
}

.social-media-icons > a {
  color: var(--text-gray);
  font-size: 16px;
  font-weight: 600;
}

.social-media-icons {
  text-align: center;
  gap: 0.25em;
}

</style>

<template>
  <footer class="container">
    <section class="copy-write-text">
      © 2023 Book Darbar Inc. All rights reserved.
    </section>
    <section class="links">
      <router-link to="/">Privacy</router-link>
      <router-link to="/">Terms of service</router-link>
      <router-link to="/">Directions</router-link>
      <router-link to="/">Contact Us</router-link>
    </section>
    <section class="social-media-icons">
      <router-link to="/">
        <i class="fa-brands fa-instagram"></i>
      </router-link>
      <router-link to="/">
        <i class="fa-brands fa-facebook"></i>
      </router-link>
      <router-link to="/">
        <i class="fa-brands fa-twitter"></i>
      </router-link>
    </section>
  </footer>
</template>
