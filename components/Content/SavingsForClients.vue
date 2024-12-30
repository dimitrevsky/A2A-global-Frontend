<template>
  <section class="savings">
    <div class="savings__title">
      <p>That’s how much we saved  for our global merchants:</p>
    </div>
    <div class="savings__money-display">
      <div class="savings__digit-container">
        <span class="savings__position-center"> $ </span>
      </div>
      <div v-for="(digit, index) in moneyDigits" :key="index" class="savings__money-display__container">
        <div class="savings__digit-container" :class="{ 'savings__digit-container--animate': isAnimating[index] }">
          <div class="savings__position-center">
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
.savings {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;
  max-width: 100%;
}

.savings__title {
  max-width: 100%;
  font-size: calc(21.35937px + 1.77083vw);
  letter-spacing: -1px;
  max-width: 700px;
  font-weight: 600;
}

.savings__title > p {
  text-align: center;
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  letter-spacing: -2px;
}

.savings__money-display {
  display: flex;
  justify-content: center;
  letter-spacing: -3px;
  font-weight: 700;
  line-height: 90%;
  color: #000;
  overflow: hidden;
  gap: 8px;
}

.savings__digit-container {
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

.savings__money-display__container:nth-child(3n) {
  margin-right: 32px;
}

.savings__money-display__container:nth-child(1) {
  margin-left: 32px;
}

.savings__digit-container--animate {
  animation: slideUp 0.2s ease-in-out forwards;
}

.savings__position-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
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
  .savings__money-display {
    gap: 5px;
    margin-left: 16px;
  }

  .savings__digit-container {
    width: 61px;
    height: 91px;
  }

  .savings__money-display > .savings__money-display__container:nth-child(3n) {
    margin-right: 16px;
  }
}

@media (max-width: 644px) {
  .savings__money-display {
    gap: 2px;
  }

  .savings__digit-container {
    width: 51px;
    height: 91px;
  }
}

@media (max-width: 536px) {
  .savings__digit-container {
    width: 36px;
    height: 61px;
  }
}

@media (max-width: 426px) {
  .savings__digit-container {
    width: 33px;
    height: 61px;
  }
}

@media (max-width: 375px) {
  .savings__digit-container {
    border-radius: 12px;
    width: 28px;
    height: 49px;
  }
}
</style>
