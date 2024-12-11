<template>
  <section class="main__form-wrapper">
    <div>
      <h1>Future of payments happening now</h1>
      <p>Fill in the form to join the A2A.Global community and our founders will contact you</p>
    </div>
    <div>
      <form @submit="handleSubmit" class="main__form">
        <div class="main__form__input-group">
          <input
            type="text"
            placeholder="What is your name?"
            v-model="name"
            @input="onInputChange('name')"
            :class="{ 'input-invalid': isNameValid === false }"
          />
          <p v-if="isSubmitAttempted && isNameValid === false" class="error-message">Пожалуйста, введите имя</p>
        </div>

        <div class="main__form__input-group">
          <input
            type="tel"
            placeholder="Введите номер телефона"
            v-model="phoneNumber"
            @input="onInputChange('phoneNumber')"
            :class="{ 'input-invalid': isPhoneNumberValid === false }"
          />
          <p v-if="isSubmitAttempted && isPhoneNumberValid === false" class="error-message">
            Пожалуйста, введите номер телефона
          </p>
        </div>

        <div class="input-container">
          <textarea
            placeholder="Other information"
            v-model="otherInformation"
            :class="{ 'input-invalid': isOtherInformationValid === false }"
            class="main__form__other-info"
          ></textarea>
          <p v-if="isSubmitAttempted && isOtherInformationValid === false" class="error-message">
            Дополнительная информация не может быть пустой
          </p>
        </div>

        <div>
          <input type="submit" value="Send" class="submit-btn" :class="{ 'submit-btn--error': !isFormValid }" />
        </div>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";

const name = ref("");
const phoneNumber = ref("");
const otherInformation = ref("");

const isSubmitAttempted = ref(false);

const validateName = (name) => /^[A-Za-zА-Яа-яЁё\s]+$/.test(name);

const validatePhoneNumber = (phoneNumber) => /^\d+$/.test(phoneNumber);

const isOtherInformationValid = computed(() => otherInformation.value.trim() !== "");

const isNameValid = computed(() => validateName(name.value));

const isPhoneNumberValid = computed(() => validatePhoneNumber(phoneNumber.value));

const isFormValid = computed(() => isNameValid.value && isPhoneNumberValid.value && isOtherInformationValid.value);

const onInputChange = (field) => {
  if (field === "name") {
    name.value = name.value.replace(/[^A-Za-zА-Яа-яЁё\s]/g, "");
  } else if (field === "phoneNumber") {
    phoneNumber.value = phoneNumber.value.replace(/\D/g, "");
  }
};

const handleSubmit = (event) => {
  isSubmitAttempted.value = true;

  if (!isFormValid.value) {
    event.preventDefault();
  }
};
</script>

<style scoped>
.main__form-wrapper {
  display: flex;
  flex-direction: column;
  justify-items: center;
  padding: 0 16px;
  margin: 0 auto;
  gap: 20px;
  text-align: center;
  max-width: 718px;
}

.main__form-wrapper > div > h1 {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 16px;
  font-weight: 600;
}

.main__form-wrapper > div > p {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
}

.main__form {
  display: flex;
  flex-direction: column;
  max-width: 718px;
  gap: 16px;
}

.main__form__input-group {
  display: flex;
  flex-direction: column;
  width: 100%;
}

input,
textarea {
  width: 100%;
}

input,
textarea,
.submit-btn {
  border: none;
  font-size: calc(18px + (6 + 6 * 0.7) * (100vw - 375px) / 1920);
  border-radius: 24px;
  line-height: 28.8px;
  padding: 20px;
  background-color: #f2f2f2;
  justify-self: end;
}

textarea {
  border-radius: 24px 8px 8px 24px;
  min-height: 138px;
  resize: vertical;
}

textarea::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

textarea::-webkit-scrollbar-thumb {
  background-color: #b1b1b1;
  border-radius: 4px;
  border: 2px solid #f2f2f2;
}

textarea::-webkit-scrollbar-thumb:hover {
  background-color: #636363;
}

textarea::-webkit-scrollbar-track {
  background-color: #f2f2f2;
  border-radius: 10px;
}

textarea::-webkit-scrollbar-track:hover {
  background-color: #e0e0e0;
}

.submit-btn {
  color: #fff;
  background-color: #0d72ff;
  padding: 16px 0;
  font-weight: 600;
  width: 100%;
  line-height: 1rem;
  transition: all 0.3s ease;
  cursor: pointer;
}

.submit-btn--error {
  background-color: #f2f2f2;
  color: black;
  pointer-events: none;
}

.error-message {
  color: red;
  font-size: 14px;
  margin-top: 4px;
}

@media (max-width: 842px) {
  input {
    padding: 16px;
    height: 54px;
  }

  .submit-btn {
    padding: 12px 0;
  }
}
</style>
