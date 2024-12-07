<template>
  <div class="header__nav">
    <div>Home</div>
    <div>Benefits for businesses</div>
    <div>Benefits for Payers</div>
    <div>FAQ</div>
  </div>
</template>

<script setup></script>

<style scoped>
.header__nav {
  text-wrap: nowrap;
  display: flex;
  flex-direction: row;
  gap: 48px;
}

.header__nav > * {
  cursor: pointer;
}
</style>
