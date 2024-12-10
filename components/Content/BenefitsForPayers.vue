<template>
  <section class="main__benefits__businesses">
    <div class="main__benefits__businesses_title">
      <p>Benefits for payers</p>
    </div>
    <div class="main__benefits__businesses__grid">
      <div class="grid__conteiner">
        <h1>Up tp 10%</h1>
        <p>LCashback</p>
      </div>
      <div class="grid__conteiner">
        <h1>&lt;0,05%</h1>
        <p>Higher conversion</p>
      </div>
      <div class="grid__conteiner">
        <h1>0</h1>
        <p>Integration cost</p>
      </div>
      <div class="grid__conteiner">
        <h1>0,001 sec</h1>
        <p>Instant payments</p>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.main__benefits__businesses_title {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 1em;
}

.main__benefits__businesses__grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(364px, 1fr));
  gap: calc(5px + 0.1vw);
}

.grid__conteiner {
  max-width: 100%;
  background-color: var(--conteiner-background-color);
  padding: 1.6vw;
  padding-bottom: 40px;
  border-radius: 24px;
  text-wrap: nowrap;
}

.grid__conteiner > h1 {
  font-size: calc(24px + (16 + 16 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 0.7em;
}

.grid__conteiner > p {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
}

@media (max-width: 729px) {
  .main__benefits__businesses__grid {
    gap: calc(2px + 0.5vw);
  }
  .grid__conteiner {
    padding: 3vw;
  }
}
</style>
