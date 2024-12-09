<template>
  <main class="main">
    <ContentPayment />
    <ContentSavingsForClients />
  </main>
</template>

<script setup></script>

<style scoped>
.main {
  width: 100%;
  display: grid;
  margin: 0 auto;
  margin-top: 20px;
  padding-bottom: 100px;
  grid-template-columns: repeat(1, 1fr);
  justify-content: center;
  gap: calc(100px + 3vw);
}
</style>
