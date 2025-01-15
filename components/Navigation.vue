<template>
  <div class="header__nav">
    <div class="header__nav-item" @click="handleClick">
      <a href="#who">Who We Are</a>
    </div>
    <div class="header__nav-item" @click="handleClick">
      <a href="#banks">What We Offer For Banks</a>
    </div>
    <div class="header__nav-item" @click="handleClick">
      <a href="#merchants">What We Offer For Merchants</a>
    </div>
  </div>
</template>

<script setup>
import { defineEmits } from "vue";

const emit = defineEmits();

const handleClick = (event) => {
  emit("closeMenu");

  event.preventDefault();
  const targetId = event.target.getAttribute("href").slice(1);
  const targetElement = document.getElementById(targetId);
  if (targetElement) {
    window.scrollTo({
      top: targetElement.offsetTop - 100,
      behavior: "smooth",
    });
  }
};
</script>

<style scoped>
.header__nav {
  display: flex;
  flex-direction: row;
  gap: 48px;
}

.header__nav-item {
  cursor: pointer;
  font-weight: 500;
  transition: color 0.3s ease-in-out;
}

.header__nav-item:hover {
  color: #2d84ff;
}

a {
  text-wrap: nowrap;
  font-size: inherit;
  transition: color 0.2s ease-in-out;
}

a:active,
a:hover,
a {
  text-decoration: none;
  color: var(--text-color);
}

a:hover {
  color: #0d72ff;
}
</style>
