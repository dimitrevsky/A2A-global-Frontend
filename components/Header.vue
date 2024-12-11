<template>
  <header class="header">
    <div class="header__logo">
      <img src="/assets/img/Logo.svg" alt="Logo" />
    </div>

    <Navigation class="header__nav" />

    <div>
      <Button class="header__btn" />
    </div>
    <div class="header__sidebar">
      <Sidebar />
    </div>
  </header>
</template>

<script setup>
import Navigation from "./Navigation.vue";
import Sidebar from "./Sidebar.vue";
import Button from "./UI/Button.vue";
</script>

<style scoped>
.header {
  position: sticky;
  top: 0;
  width: 100%;
  padding: 24px 64px;
  font-size: 24px;
  display: flex;
  gap: 22px;
  background-color: #fff;
  justify-content: space-between;
  align-items: center;
  line-height: 21.6px;
  z-index: 100;
}

.header__logo {
  font-weight: 800;
  pointer-events: none;
}

.header__logo img {
  -webkit-user-drag: none;
  user-select: none;
}
.header__btn {
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


@media (max-width: 1058px) {
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
