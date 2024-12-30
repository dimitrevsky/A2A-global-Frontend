<template>
    <button @click="handleButtonClick">
      <a href="#Form">Join A2A Global Network</a>
    </button>
</template>

<script setup>
import { defineEmits } from "vue";

const emit = defineEmits();

const handleButtonClick = (event) => {
  emit("closeMenu");

  event.preventDefault();
  const targetId = event.target.querySelector("a").getAttribute("href").slice(1);
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
button {
  border: none;
  border-radius: 24px;
  background: none;
  font-size: 24px;
  cursor: pointer;
  font-weight: 600;
  letter-spacing: -1px;
}

a {
  text-decoration: none;
  color: inherit;
  pointer-events: none;
}

</style>
