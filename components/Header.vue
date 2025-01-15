<template>
  <header class="header">
    <div class="header__logo">
      <img src="/assets/img/Logo.png" alt="Logo" />
    </div>

    <div class="header__conteiner__nav">
      <Navigation class="header__nav" />
    </div>

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
  display: flex;
  font-size: 24px;
  justify-content: space-between;
  gap: 22px;
  background-color: #fff;
  align-items: center;
  line-height: 21.6px;
  z-index: 100;
}

.header__logo {
  -webkit-user-drag: none;
  user-select: none;
}

.header__logo > img {
  max-width: 160px;
  max-height: 58px;
}

.header__btn {
  background-color: rgba(13, 114, 255, 0.15);
  padding: 12px;
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

.header__conteiner__nav {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@media (max-width: 1611px) {
  .header__nav {
    font-size: calc(22px + (2 + 2 * 0.7) * (100vw - 375px) / 1920);
    gap: 16px;
    letter-spacing: -1px;
  }

  .header__conteiner__nav {
    left: 45%;
  }
}

@media (max-width: 1385px) {
  .header__nav {
    gap: 10px;
  }
}

@media (max-width: 1337px) {
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

@media (max-width: 375px) {
  .header__logo {
    max-width: 128px;
    max-height: 47px;
  }
}
</style>
