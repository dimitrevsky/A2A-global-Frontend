<template>
  <section class="benefits__banks" id="banks">
    <div class="benefits__banks-title">
      <p class="benefits__banks-title-text">Benefits for banks</p>
    </div>
    <div class="benefits__banks-grid">
      <div class="benefits__banks-item">
        <h1 class="benefits__banks-item-value">Growth</h1>
        <p class="benefits__banks-item-description">In client base</p>
      </div>
      <div class="benefits__banks-item">
        <h1 class="benefits__banks-item-value">Low</h1>
        <p class="benefits__banks-item-description">Customer acquisition cost</p>
      </div>
      <div class="benefits__banks-item">
        <h1 class="benefits__banks-item-value">Increase</h1>
        <p class="benefits__banks-item-description">In A2A interchange revenue</p>
      </div>
      <div class="benefits__banks-item">
        <h1 class="benefits__banks-item-value">Low</h1>
        <p class="benefits__banks-item-description">Infrastructure cost</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefits__banks {
  padding: 16px;
}

.benefits__banks-title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 1em;
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__banks-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(359px, 1fr));
  gap: calc(5px + 0.1vw);
}

.benefits__banks-item {
  max-width: 100%;
  background-color: #f2f2f2;
  padding: 2.4vw;
  padding-bottom: 40px;
  border-radius: 24px;
  text-wrap: nowrap;
}

.benefits__banks-item > h1 {
  font-size: calc(24px + (16 + 16 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 0.7em;
}

.benefits__banks-item > p {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
}

.benefits__banks-item-value {
  letter-spacing: -1px;
  font-weight: 500;
  line-height: 100%;
}

.benefits__banks-item-description {
  line-height: 140%;
  color: #1b1b1b;
}

@media (max-width: 729px) {
  .benefits__banks-grid {
    gap: calc(2px + 0.5vw);
  }
  .benefits__banks-item {
    padding: 3vw;
  }
}

@media (max-width: 411px) {
  .benefits__banks-grid {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
