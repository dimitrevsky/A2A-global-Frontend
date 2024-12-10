<script setup>
import Button from "../UI/Button.vue";
</script>

<template>
  <div class="main__payment">
    <div class="main__payment__wrapper__vid">
      <video width="auto" height="100%" class="main__payment__vid" playsinline autoplay muted loop>
        <source src="/assets/video/animation1.mp4" />
      </video>
    </div>
    <div class="main__payment__info">
      <div class="text-general-style title">
        Instant payments <br />
        From account to account <br />
        No hassle!
      </div>
      <div class="text-general-style text">Accept payments from anywhere in the world with just one click.</div>
      <div>
        <Button class="main__payment__btn" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.main__payment {
  position: relative;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  gap: 40px;
}

.main__payment__wrapper__vid {
  position: relative;
  max-width: 100%;
  height: 544px;
  overflow: hidden;
  border-radius: 24px;
}

.main__payment__vid {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  border-radius: 24px;
}

.title {
  font-size: calc(28px + (28 + 28 * 0.7) * (100vw - 375px) / 1920);
  letter-spacing: -2px;
  margin-bottom: 24px;
}

.text {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
  font-weight: 400;
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
  align-items: center;
}
</style>
