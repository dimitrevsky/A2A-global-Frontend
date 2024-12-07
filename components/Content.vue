<template>
  <main class="main">
    <ContentPayment />
  </main>
</template>

<script setup></script>

<style scoped>
.main {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  justify-content: center;
  gap: calc(100px + 3vw);
  margin: 0 auto;
}
</style>
