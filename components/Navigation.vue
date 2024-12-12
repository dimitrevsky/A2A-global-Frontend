<template>
  <div class="header__nav">
    <div class="header__nav-item" @click="handleClick">
      <a href="#BenefitsForBusinesses">Benefits for businesses</a>
    </div>
    <div class="header__nav-item" @click="handleClick">
      <a href="#BenefitsForPayers">Benefits for Payers</a>
    </div>
    <div class="header__nav-item" @click="handleClick">
      <a href="#FAQ">FAQ</a>
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
  font-size: 18px;
  font-weight: 500;
  transition: color 0.3s ease-in-out;
}

.header__nav-item:hover {
  color: #2d84ff;
}

a {
  transition: color .2s ease-in-out;
  text-wrap: nowrap;
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
