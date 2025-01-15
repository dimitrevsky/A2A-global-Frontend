<template>
  <div class="who_we_are">
    <div class="who_we_are__video-wrapper">
      <video width="auto" height="100%" class="who_we_are__video" playsinline autoplay muted loop>
        <source src="/assets/video/animation1.mp4" />
      </video>
    </div>
    <div class="who_we_are__info">
      <div class="who_we_are__info__title" id="who">
        <p>Who We Are</p>
      </div>
      <div class="who_we_are__info__text">
        <p>We build an alternative payment method for global merchants</p>
        <p>We believe that account-to-account payments (A2A) should be simple, low-cost, secure and instant</p>
        <p>We connect merchants with our global network of banking partners (A2A Global Network)</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import Button from "../UI/Button.vue";
</script>

<style scoped>
.who_we_are {
  position: relative;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  gap: 40px;
}

.who_we_are__video-wrapper {
  position: relative;
  max-width: 100%;
  height: 544px;
  overflow: hidden;
  border-radius: 24px;
}

.who_we_are__video {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  border-radius: 24px;
}

.who_we_are__info__title {
  font-size: calc(18.70313px + 2.47917vw);
  letter-spacing: -1px;
  margin-bottom: 24px;
  font-weight: 600;
  line-height: 120%;
  margin-bottom: 24px;
  text-align: center;
}

.who_we_are__info__text {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
  font-weight: 500;
  max-width: 683px;
  display: flex;
  flex-direction: column;
  gap: 28px;
  margin-bottom: 40px;
  text-align: center;
  color: #727272;
}

.who_we_are__button {
  color: #ffffff;
  width: 160px;
  background-color: rgb(13, 114, 255);
  padding: 16px 56px;
  transition: all 0.1s ease-in-out;
  line-height: 29.05px;
  justify-self: center;
}

.who_we_are__info {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
