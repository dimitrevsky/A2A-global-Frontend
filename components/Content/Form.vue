<template>
  <section class="main__form-wrapper" id="Form">
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
            :class="{ 'input-invalid': !isNameValid }"
          />
          <p v-if="isSubmitAttempted && !isNameValid" class="error-message">Please enter a name</p>
        </div>

        <div class="main__form__input-group">
          <input
            type="tel"
            placeholder="Phone number"
            v-model="phoneNumber"
            @input="onInputChange('phoneNumber')"
            :class="{ 'input-invalid': !isPhoneNumberValid }"
          />
          <p v-if="isSubmitAttempted && !phoneNumber" class="error-message">Please enter your phone number</p>
        </div>

        <div class="input-container">
          <textarea
            placeholder="Other information"
            v-model="otherInformation"
            :class="{ 'input-invalid': !isOtherInformationValid }"
            class="main__form__other-info"
          ></textarea>
        </div>

        <div>
          <input type="submit" value="Send" class="submit-btn" />
        </div>

        <p
          style="color: #0d72ff"
          v-if="submissionStatus"
          :class="submissionStatus.success ? 'success-message' : 'error-message'"
        >
          {{ submissionStatus.message }}
        </p>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";
import { send } from "@emailjs/browser";

const name = ref("");
const phoneNumber = ref("");
const otherInformation = ref("");
const isSubmitAttempted = ref(false);
const submissionStatus = ref(null);

const validateName = (name) => /^[A-Za-zА-Яа-яЁё\s]+$/.test(name);
// Убираем валидацию для номера телефона
const isOtherInformationValid = computed(() => otherInformation.value.trim() !== "");
const isNameValid = computed(() => validateName(name.value));
// Для phoneNumber не проверяем с помощью регулярных выражений
const isFormValid = computed(() => isNameValid.value && phoneNumber.value.trim() !== "");

const onInputChange = (field) => {
  if (field === "name") {
    name.value = name.value.replace(/[^A-Za-zА-Яа-яЁё\s]/g, "");
  } else if (field === "phoneNumber") {
    // Здесь не фильтруем символы, так как нам нужно разрешить ввод любых символов
  }
};

const handleSubmit = async (event) => {
  event.preventDefault();
  isSubmitAttempted.value = true;

  if (!isFormValid.value) return;

  try {
    const serviceId = "A2A.global";
    const templateId = "template_ebe1bnk";
    const userId = "E0jz6DO7c3Iz5LPoA";

    const response = await send(
      serviceId,
      templateId,
      {
        name: name.value,
        phone_number: phoneNumber.value,
        other_information: otherInformation.value,
      },
      userId
    );

    submissionStatus.value = { success: true, message: "Your message has been successfully sent!" };
    console.debug("Message sent successfully", response);
  } catch (error) {
    submissionStatus.value = {
      success: false,
      message: "There was an error sending the message. Please try again.",
    };
    console.error("Error sending message", error);
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
}

.main__form-wrapper > div > h1 {
  font-size: calc(28px + (20 + 20 * 0.7) * (100vw - 375px) / 1920);
  text-align: center;
  margin-bottom: 16px;
  font-weight: 600;
  letter-spacing: -1px;
}

.main__form-wrapper > div > p {
  font-size: calc(16px + (4 + 4 * 0.7) * (100vw - 375px) / 1920);
}

.main__form {
  display: flex;
  flex-direction: column;
  max-width: 718px;
  gap: 16px;
  margin: 0 auto;
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
  border-radius: 24px;
  height: 191px;
  resize: none;
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
  padding: 24px 0;
  font-weight: 600;
  width: 100%;
  line-height: 1rem;
  transition: all 0.3s ease;
  cursor: pointer;
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
