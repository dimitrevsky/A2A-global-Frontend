<template>
  <div>
    <button @click="toggleMenu" class="hamburger_button">
      <span :class="['bar', { active: isOpen }]"></span>
      <span :class="['bar', { active: isOpen }]"></span>
      <span :class="['bar', { active: isOpen }]"></span>
    </button>
    <div class="sidebar" :class="{ 'is-open': isOpen }">
      <div class="sidebar-content" :style="{ opacity: isOpen ? 1 : 0 }">
        <Navigation @closeMenu="closeMenu" />
        <Button @closeMenu="closeMenu" class="header__btn" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Navigation from "./Navigation.vue";
import Button from "./UI/Button.vue";

const isOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

const closeMenu = () => {
  isOpen.value = false;
};
</script>

<style scoped>
.hamburger_button {
  background: transparent;
  right: 20px;
  border: none;
  cursor: pointer;
  z-index: 1001;
  transition: transform 0.3s ease-in-out;
}

.bar {
  display: block;
  width: 30px;
  height: 3px;
  margin: 4px 0;
  border-radius: 12px;
  background-color: #000000;
  transition: transform 0.3s ease-in-out;
}

.bar.active:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.bar.active:nth-child(2) {
  opacity: 0;
}

.bar.active:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

.header__nav {
  flex-direction: column;
}

.sidebar {
  position: fixed;
  top: 93px;
  right: 0;
  width: 100%;
  height: 100%;
  background-color: #fff;
  opacity: 0;
  transition: opacity 0.3s ease;
  pointer-events: none;
}

.sidebar.is-open {
  pointer-events: auto;
  opacity: 1;
}

.sidebar-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: rgb(0, 0, 0);
  text-align: center;
}

.sidebar__menu {
  list-style: none;
  padding: 0;
  margin: 0;
}

.header__btn {
  margin-top: 48px;
  color: #0d72ff;
  background-color: rgba(13, 114, 255, 0.15);
  padding: 16px 56px;
  transition: all 0.1s ease-in-out;
  transition: box-shadow 0.01s;
  border-radius: 32px;
  line-height: 29.05px;
}

.header__btn:hover {
  background-color: rgba(13, 114, 255, 0.4);
}
</style>
