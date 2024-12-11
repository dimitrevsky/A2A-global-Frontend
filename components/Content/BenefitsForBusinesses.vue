<template>
  <section class="benefits__businesses" id="BenefitsForBusinesses">
    <div class="benefits__businesses-title">
      <p class="benefits__businesses-title-text">Benefits for businesses</p>
    </div>
    <div class="benefits__businesses-grid">
      <div class="benefits__businesses-item">
        <h1 class="benefits__businesses-item-value">0,5% + 1 cent</h1>
        <p class="benefits__businesses-item-description">Low fees per transaction</p>
      </div>
      <div class="benefits__businesses-item">
        <h1 class="benefits__businesses-item-value">>x2</h1>
        <p class="benefits__businesses-item-description">Higher conversion</p>
      </div>
      <div class="benefits__businesses-item">
        <h1 class="benefits__businesses-item-value">0</h1>
        <p class="benefits__businesses-item-description">Integration cost</p>
      </div>
      <div class="benefits__businesses-item">
        <h1 class="benefits__businesses-item-value">0,001 sec</h1>
        <p class="benefits__businesses-item-description">Instant payments</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefits__businesses {
  padding: 16px;
}

.benefits__businesses-title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 1em;
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__businesses-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(359px, 1fr));
  gap: calc(5px + 0.1vw);
}

.benefits__businesses-item {
  max-width: 100%;
  background-color: #f2f2f2;
  padding: 1.6vw;
  padding-bottom: 40px;
  border-radius: 24px;
  text-wrap: nowrap;
}

.benefits__businesses-item:nth-child(1) {
  background-color: #0d72ff;
  color: #fff;
}

.benefits__businesses-item:nth-child(1) > p {
  background-color: #0d72ff;
  color: #fff;
}

.benefits__businesses-item-value {
  font-size: calc(24px + (16 + 16 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 0.7em;
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__businesses-item-description {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
  line-height: 140%;
  color: #1b1b1b;
}
@media (max-width: 729px) {
  .benefits__businesses-grid {
    gap: calc(2px + 0.5vw);
  }
  .benefits__businesses-item {
    padding: 3vw;
  }
}

@media (max-width: 411px) {
  .benefits__businesses-grid {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
