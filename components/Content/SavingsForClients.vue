<template>
  <section>
    <div class="title">
      <p>Cumulative savings for our clients as of today</p>
    </div>
    <div class="main__money-display">
      <div class="digit-container">
        <span class="position_center"> $ </span>
      </div>
      <div v-for="(digit, index) in moneyDigits" :key="index" class="main__money-display_container">
        <div class="digit-container" :class="{ 'animate-change': isAnimating[index] }">
          <div class="position_center">
            {{ digit }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";

const moneyDigits = ref([2, 3, 4, 5, 6, 7, 8, 9]);
const isAnimating = ref(Array(moneyDigits.value.length).fill(false));

function getRandomIncrease() {
  return [13, 21, 35, 11, 3, 99][Math.floor(Math.random() * 3)];
}

function increaseMoneyValue() {
  let carry = getRandomIncrease();
  let newMoneyDigits = [...moneyDigits.value];

  for (let i = newMoneyDigits.length - 1; i >= 0; i--) {
    newMoneyDigits[i] += carry;
    if (newMoneyDigits[i] >= 10) {
      newMoneyDigits[i] %= 10;
      carry = 1;
    } else {
      carry = 0;
      break;
    }
  }

  const previousMoneyDigits = [...moneyDigits.value];
  moneyDigits.value = newMoneyDigits;

  isAnimating.value = newMoneyDigits.map((digit, index) => digit !== previousMoneyDigits[index]);

  setTimeout(() => {
    isAnimating.value = Array(moneyDigits.value.length).fill(false);
  }, 300);
}

onMounted(() => {
  setInterval(increaseMoneyValue, 3000);
});
</script>

<style scoped>
.main__money-display {
  display: flex;
  justify-self: center;
  align-items: center;
  color: #000;
  overflow: hidden;
  gap: 8px;
}

.digit-container {
  width: 91px;
  height: 91px;
  display: flex;
  background-color: #f2f2f2;
  padding: 10px;
  border-radius: 24px;
  line-height: 28.8px;
  font-size: calc(32px + (16 + 16 * 0.7) * (100vw - 375px) / 1920);
  font-weight: bold;
  position: relative;
}

.main__money-display_container:nth-child(3n) {
  margin-right: 32px;
}
.main__money-display_container:nth-child(1) {
  margin-left: 32px;
}

.digit-container.animate-change {
  animation: slideUp 0.2s ease-in-out forwards;
}

.position_center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.title {
  max-width: 100%;
  margin-bottom: calc(24px + 1vw);
}

.title > p {
  text-align: center;
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  letter-spacing: -2px;
}

@keyframes slideUp {
  0% {
    opacity: 1;
    transform: translateY(0);
  }
  50% {
    opacity: 0;
    transform: translateY(-91px);
  }
}

@media (max-width: 1014px) {
  .main__money-display {
    gap: 5px;
    margin-left: 16px;
  }

  .digit-container {
    width: 61px;
    height: 91px;
  }

  .main__money-display > .main__money-display_container:nth-child(3n) {
    margin-right: 16px;
  }
}

@media (max-width: 644px) {
  .main__money-display {
    gap: 2px;
  }

  .digit-container {
    width: 51px;
    height: 91px;
  }
}

@media (max-width: 536px) {
  .digit-container {
    width: 36px;
    height: 61px;
  }
}

@media (max-width: 426px) {
  .digit-container {
    width: 33px;
    height: 61px;
  }
}

@media (max-width: 375px) {
  .digit-container {
    border-radius: 12px;
    width: 31px;
    height: 49px;
  }
}
</style>
