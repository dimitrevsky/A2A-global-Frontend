<script setup>
import Button from "../UI/Button.vue";
</script>

<template>
  <div class="main__payment">
    <div class="main__payment__img">
      <!-- <img src="" alt=""> -->
    </div>
    <div class="main__payment__info">
      <div class="text-general-style title">
        Instant payments <br />
        From account to account <br />
        No hassle!
      </div>
      <div class="text-general-style text">Accept payments from anywhere in the world with just one click.</div>

      <div class="btn_position">
        <Button class="main__payment__btn" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.main__payment {
  max-width: 100%;
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.main__payment__img {
  min-width: 100%;
  height: 555px;
  background-image: url("../../assets/img/ContentBack.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  border-radius: 24px;
}

.title {
  font-size: calc(28px + (28 + 28 * 0.7) * (100vw - 375px) / 1920);
  letter-spacing: -2px;
  margin-bottom: 24px;
}

.text {
  font-weight: 400;
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 40px;
}

.main__payment__btn {
  color: #ffffff;
  width: 160px;
  background-color: rgb(13, 114, 255);
  padding: 16px 56px;
  transition: all 0.1s ease-in-out;
  line-height: 29.05px;
  justify-self: center;
}

.main__payment__info {
  display: flex;
  flex-direction: column;
  align-items: center
}
</style>
