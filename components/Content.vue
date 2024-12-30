<template>
  <main class="main">
    <WhoWeAre />
    <SavingsForClients />
    <BenefitsForMerchants />
    <BenefitsForPayers />
    <BenefitsForBanks />
    <Form />
    <!-- FAQ -->
    <footer class="main__footer">
      A2A Global Inc (United States, Delaware) <br />
      All rights reserved 2025 ©
    </footer>
  </main>
</template>

<script setup>
import BenefitsForPayers from "./Content/BenefitsForPayers.vue";
import SavingsForClients from "./Content/SavingsForClients.vue";
import Form from "./Content/Form.vue";
import WhoWeAre from "./Content/WhoWeAre.vue";
import BenefitsForMerchants from "./Content/BenefitsForMerchants.vue";
import BenefitsForBanks from "./Content/BenefitsForBanks.vue";
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
  font-size: calc(18px + (6 + 6 * 0.7) * (100vw - 375px) / 1920);
  color: #656565;
}
</style>
