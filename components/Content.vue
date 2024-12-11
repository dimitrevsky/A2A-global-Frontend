<template>
  <main class="main">
    <Payment />
    <SavingsForClients />
    <BenefitsForBusinesses />
    <BenefitsForPayers />
    <Form />
    <FAQ />
    <footer class="main__footer">A2A.Global All rights reserved 2024(с)</footer>
  </main>
</template>

<script setup>
import BenefitsForBusinesses from "./Content/BenefitsForBusinesses.vue";
import BenefitsForPayers from "./Content/BenefitsForPayers.vue";
import FAQ from "./Content/FAQ.vue";
import SavingsForClients from "./Content/SavingsForClients.vue";
import Form from "./Content/Form.vue";
import Payment from "./Content/Payment.vue";
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

.main__footer {
  text-align: center;
}
</style>
