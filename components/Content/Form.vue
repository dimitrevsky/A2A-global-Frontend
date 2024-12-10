<template>
  <section class="main__form_wrapper">
    <div>
      <h1>Future of payments happening now</h1>
      <p>Fill in the form to join the A2A.Global community and our founders will contact you</p>
    </div>
    <div>
      <form action="" class="main__form">
        <div class="main__form__name">
          <input type="text" placeholder="What is your name?" class="input-width input" />
        </div>
        <div class="main__form__phone-number">
          <input type="text" placeholder="+1 234 567-89-00" class="input-width input" />
        </div>
        <div class="input-container">
          <textarea
            placeholder="Other information"
            name="131"
            style="height: 200px"
            class="main__form__other-info input-width input"
          ></textarea>
        </div>
        <div>
          <input type="submit" value="Send" class="submit-btn" />
        </div>
      </form>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.main__form_wrapper {
  display: flex;
  flex-direction: column;
  padding: 0 16px;
  text-align: center;
  margin: 0 auto;
  gap: 20px;
}

.main__form_wrapper > div > h1 {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  margin-bottom: 16px;
  font-weight: 600;
}

.main__form_wrapper > div > p {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
}

.main__form {
  display: flex;
  max-width: 100%;
  flex-direction: column;
  gap: 16px;
}

input,
textarea,
.submit-btn {
  border: none;
  font-size: calc(18px + (6 + 6 * 0.7) * (100vw - 375px) / 1920);
  border-radius: 24px;
  line-height: 28.8px;
  resize: vertical;
}

textarea {
  border-radius: 24px 10px 10px 24px;
  min-height: 138px;
}

.input-width {
  width: 100%;
}

.input {
  padding: 20px;
  height: 69px;
  background-color: #f2f2f2;
}

textarea::-webkit-scrollbar {
  width: 8px;
  height: 8px;
  margin-right: 10px;
}

textarea::-webkit-scrollbar-thumb {
  background-color: #888;
  border-radius: 10px;
  border: 2px solid #ccc;
}

textarea::-webkit-scrollbar-track {
  background-color: #f1f1f1;
  border-radius: 10px;
}

textarea::-webkit-scrollbar-thumb:hover {
  background-color: #555;
}

textarea::-webkit-scrollbar-thumb:active {
  background-color: #333;
}

.submit-btn {
  background-color: #0d72ff;
  color: #ffffff;
  padding: 16px 0;
  font-weight: 600;
  width: 100%;
  line-height: 1rem;
}

@media (max-width: 842px) {
  .input {
    padding: 16px;
    height: 54px;
  }

  .submit-btn {
    padding: 12px 0;
  }
}
</style>
