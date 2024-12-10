<template>
  <main class="main">
    <ContentPayment />
    <ContentSavingsForClients />
    <BenefitsForBusinesses />
  </main>
</template>

<script setup>
import BenefitsForBusinesses from './Content/BenefitsForBusinesses.vue';
</script>

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
