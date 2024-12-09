<script setup>
import Navigation from "./Navigation.vue";
import Sidebar from "./Sidebar.vue";
import Button from "./UI/Button.vue";
</script>

<template>
  <header class="header">
    <div class="header__logo"><img src="/assets/img/Logo.svg" alt="Logo">
    </div>

    <Navigation />

    <div>
      <Button class="header__btn" />
    </div>
    <div class="header__sidebar">
      <Sidebar />
    </div>
  </header>
</template>

<style scoped>
.header {
  position: sticky;
  top: 0;
  width: 100%;
  padding: 24px 64px;
  font-size: 24px;
  display: flex;
  gap: 22px;
  background-color: var(--web-site-background);
  justify-content: space-between;
  align-items: center;
  line-height: 21.6px;
  z-index: 1;
}

.header__logo {
  font-weight: 800;
}

.header__btn {
  color: #0d72ff;
  background-color: rgba(13, 114, 255, 0.15);
  padding: 16px 56px;
  transition: all 0.1s ease-in-out;
  transition: box-shadow 0.01s;
  line-height: 29.05px;
}

.header__btn:hover {
  background-color: rgba(13, 114, 255, 0.4);
}

.header__sidebar {
  display: none;
}

@media (max-width: 1258px) {
  .header__nav {
    display: none;
  }

  .header {
    padding: 16px;
  }

  .header__btn {
    display: none;
  }

  .header__sidebar {
    display: flex;
  }
}
</style>
