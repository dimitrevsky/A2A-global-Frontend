<template>
  <section class="benefits__payers" id="BenefitsForPayers">
    <div class="benefits__payers-title">
      <p class="benefits__payers-title-text">Benefits For Payers</p>
    </div>
    <div class="benefits__payers-grid">
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">Up to 10%</h1>
        <p class="benefits__payers-item-description">Cashback</p>
      </div>
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">&lt;0,05%</h1>
        <p class="benefits__payers-item-description">FX Fees</p>
      </div>
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">0 Hassle</h1>
        <p class="benefits__payers-item-description">No card, only mobile phone</p>
      </div>
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">100%</h1>
        <p class="benefits__payers-item-description">Secure: 2FA, no card number exposed</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefits__payers {
  padding: 16px;
}

.benefits__payers-title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 1em;
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__payers-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(359px, 1fr));
  gap: calc(5px + 0.1vw);
}

.benefits__payers-item {
  max-width: 100%;
  background-color: #f2f2f2;
  padding: 2.4vw;
  padding-bottom: 40px;
  border-radius: 24px;
  text-wrap: nowrap;
}

.benefits__payers-item > h1 {
  font-size: calc(24px + (16 + 16 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 0.7em;
}

.benefits__payers-item > p {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
}

.benefits__payers-item-value {
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__payers-item-description {
  line-height: 140%;
  color: #1b1b1b;
}

@media (max-width: 729px) {
  .benefits__payers-grid {
    gap: calc(2px + 0.5vw);
  }
  .benefits__payers-item {
    padding: 3vw;
  }
}

@media (max-width: 411px) {
  .benefits__payers-grid {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
