<template>
  <section class="benefits__merchants" id="merchants">
    <div class="benefits__merchants-title">
      <p class="benefits__merchants-title-text">Benefits for merchants</p>
    </div>
    <div class="benefits__merchants-grid">
      <div class="benefits__merchants-item">
        <h1 class="benefits__merchants-item-value">0,5% + 1 cent</h1>
        <p class="benefits__merchants-item-description">Low fees per transaction</p>
      </div>
      <div class="benefits__merchants-item">
        <h1 class="benefits__merchants-item-value">>x2</h1>
        <p class="benefits__merchants-item-description">Higher conversion at checkout</p>
      </div>
      <div class="benefits__merchants-item">
        <h1 class="benefits__merchants-item-value">0</h1>
        <p class="benefits__merchants-item-description">Integration cost is on us</p>
      </div>
      <div class="benefits__merchants-item">
        <h1 class="benefits__merchants-item-value">1 day</h1>
        <p class="benefits__merchants-item-description">Instant payments</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefits__merchants {
  padding: 16px;
}

.benefits__merchants-title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 1em;
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__merchants-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(359px, 1fr));
  gap: calc(5px + 0.1vw);
}

.benefits__merchants-item {
  max-width: 100%;
  background-color: #f2f2f2;
  padding: 2.4vw;
  padding-bottom: 40px;
  border-radius: 24px;
  text-wrap: nowrap;
}

.benefits__merchants-item:nth-child(1) {
  background-color: #0d72ff;
  color: #fff;
}

.benefits__merchants-item:nth-child(1) > p {
  background-color: #0d72ff;
  color: #fff;
}

.benefits__merchants-item-value {
  font-size: calc(24px + (16 + 16 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 0.7em;
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__merchants-item-description {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
  line-height: 140%;
  color: #1b1b1b;
}
@media (max-width: 729px) {
  .benefits__merchants-grid {
    gap: calc(2px + 0.5vw);
  }
  .benefits__merchants-item {
    padding: 3vw;
  }
}

@media (max-width: 411px) {
  .benefits__merchants-grid {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
