<template>
  <div class="header__nav">
    <div class="header__nav__item">Home</div>
    <div class="header__nav__item">Benefits for businesses</div>
    <div class="header__nav__item">Benefits for Payers</div>
    <div class="header__nav__item">FAQ</div>
  </div>
</template>

<style scoped>
.header__nav {
  display: flex;
  flex-direction: row;
  gap: 48px;
}

.header__nav__item {
  cursor: pointer;
  font-size: 18px;
  font-weight: 500;
  transition: color 0.3s ease-in-out;
}

.header__nav__item:hover {
  color: #0d72ff;
}
</style>
