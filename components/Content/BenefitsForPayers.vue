<template>
  <section class="benefits__payers">
    <div class="benefits__payers-title">
      <p class="benefits__payers-title-text">Benefits for payers</p>
    </div>
    <div class="benefits__payers-grid">
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">Up to 10%</h1>
        <p class="benefits__payers-item-description">Cashback</p>
      </div>
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">&lt;0,05%</h1>
        <p class="benefits__payers-item-description">Higher conversion</p>
      </div>
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">0</h1>
        <p class="benefits__payers-item-description">Integration cost</p>
      </div>
      <div class="benefits__payers-item">
        <h1 class="benefits__payers-item-value">0,001 sec</h1>
        <p class="benefits__payers-item-description">Instant payments</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefits__payers-title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 1em;
}

.benefits__payers-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(364px, 1fr));
  gap: calc(5px + 0.1vw);
}

.benefits__payers-item {
  max-width: 100%;
  background-color: #f2f2f2;
  padding: 1.6vw;
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

@media (max-width: 729px) {
  .benefits__payers-grid {
    gap: calc(2px + 0.5vw);
  }
  .benefits__payers-item {
    padding: 3vw;
  }
}
</style>
