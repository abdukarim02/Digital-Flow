<template>
    <section class="contacts">
      <div class="contacts__content">
        <div class="contacts__content_form">
          <form class="form" @submit.prevent="submitForm">
            <h2 class="info__title title">Заявка</h2>
            <div class="form__body">
              <div class="form__group">
                <label class="form__group-name" for="name">Ваше имя</label>
                <input
                  class="form__group-text"
                  type="text"
                  id="name"
                  v-model="form.name"
                  :class="{ 'is-invalid': errors.name }"
                  aria-describedby="nameError"
                />
                <p id="nameError" class="error-message" v-if="errors.name">{{ errors.name }}</p>
              </div>
              <div class="form__group">
                <label class="form__group-name" for="email">Ваш Email</label>
                <input
                  class="form__group-text"
                  type="email"
                  id="email"
                  v-model="form.email"
                  :class="{ 'is-invalid': errors.email }"
                  aria-describedby="emailError"
                />
                <p id="emailError" class="error-message" v-if="errors.email">{{ errors.email }}</p>
              </div>
              <div class="form__group">
                <label class="form__group-name" for="masegs">Ваше сообщение</label>
                <textarea
                  class="form__group-text"
                  id="masegs"
                  v-model="form.masegs"
                  :class="{ 'is-invalid': errors.masegs }"
                  aria-describedby="masegsError"
                ></textarea>
                <p id="masegsError" class="error-message" v-if="errors.masegs">{{ errors.masegs }}</p>
              </div>
              <button type="submit" class="form-submit btn">
                ОТПРАВИТЬ
                <svg width="8" height="13" viewBox="0 0 8 13" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M7.33352 6.03176L1.99337 0.691706C1.86985 0.568097 1.70498 0.5 1.52917 0.5C1.35337 0.5 1.18849 0.568097 1.06498 0.691706L0.671718 1.08487C0.415818 1.34107 0.415818 1.75745 0.671718 2.01326L5.15597 6.49751L0.666742 10.9867C0.543231 11.1104 0.475037 11.2751 0.475037 11.4508C0.475037 11.6267 0.543231 11.7915 0.666742 11.9152L1.06001 12.3083C1.18362 12.4319 1.3484 12.5 1.5242 12.5C1.7 12.5 1.86488 12.4319 1.98839 12.3083L7.33352 6.96336C7.45732 6.83936 7.52532 6.6738 7.52493 6.49781C7.52532 6.32112 7.45732 6.15566 7.33352 6.03176Z"
                  />
                </svg>
              </button>
            </div>
          </form>
        </div>
        <div class="contacts__content-info">
            <div class="info">
                <h2 class="info__title title">Спец предложения </h2>
                <div class="info__wrap">
                    <div class="info__wrap_flex">
                        <a href="#" class="link"></a>
                        <div class="flex">
                            <h5 class="flex__name">Landing Page</h5>
                            <p class="flex__text">продающая посадочная страница.</p>
                            <p class="flex__discount">150 000 ₸</p>
                            <p class="flex__price">150 000 ₸</p>
                        </div>
                    </div>
                    <div class="info__wrap_flex">
                        <a href="#" class="link"></a>
                        <div class="flex">
                            <h5 class="flex__name">Landing Page</h5>
                            <p class="flex__text">продающая посадочная страница.</p>
                            <p class="flex__discount">150 000 ₸</p>
                            <p class="flex__price">150 000 ₸</p>
                        </div>
                    </div>
                    <div class="info__wrap_flex">
                        <a href="#" class="link"></a>
                        <div class="flex">
                            <h5 class="flex__name">Landing Page</h5>
                            <p class="flex__text">продающая посадочная страница.</p>
                            <p class="flex__discount">150 000 ₸</p>
                            <p class="flex__price">150 000 ₸</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
      </div>
    </section>
    <section v-if="isVisible" class="confirmation">
      <div class="confirmation__content container">
        <div class="confirmation__content-forma">
          <div class="form">
            <div class="form-logo">
              <svg width="48" height="36" viewBox="0 0 48 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M47.2971 1.07798C46.3599 0.140672 44.8404 0.140672 43.903 1.07798L15.1495 29.8318L4.09711 18.7794C3.15989 17.8421 1.64039 17.8422 0.702984 18.7794C-0.234328 19.7166 -0.234328 21.2361 0.702984 22.1734L13.4524 34.9227C14.3894 35.8599 15.91 35.8592 16.8465 34.9227L47.2971 4.47211C48.2344 3.53489 48.2343 2.0153 47.2971 1.07798Z" fill="white" />
              </svg>
            </div>
            <div class="form__info">
              <h5 class="form__info-title">Успешно оформлено!</h5>
              <p class="form__info-text">Ваш заказ успешно оформлен! Спасибо что выбрали именно нас.</p>
            </div>
            <div class="form__footer">
              <button @click="hideBlock" type="submit" class="form__footer-btn btn">
                Вернуться на главную
                <svg width="8" height="13" viewBox="0 0 8 13" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M7.33352 6.03176L1.99337 0.691706C1.86985 0.568097 1.70498 0.5 1.52917 0.5C1.35337 0.5 1.18849 0.568097 1.06498 0.691706L0.671718 1.08487C0.415818 1.34107 0.415818 1.75745 0.671718 2.01326L5.15597 6.49751L0.666742 10.9867C0.543231 11.1104 0.475037 11.2751 0.475037 11.4508C0.475037 11.6267 0.543231 11.7915 0.666742 11.9152L1.06001 12.3083C1.18362 12.4319 1.3484 12.5 1.5242 12.5C1.7 12.5 1.86488 12.4319 1.98839 12.3083L7.33352 6.96336C7.45732 6.83936 7.52532 6.6738 7.52493 6.49781C7.52532 6.32112 7.45732 6.15566 7.33352 6.03176Z"
                  />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>
<script>
import { ref } from "vue";

export default {
  setup() {
    const form = ref({
      name: "",
      email: "",
      masegs: "",
    });

    const errors = ref({
      name: "",
      email: "",
      masegs: "",
    });

    const isVisible = ref(false); // Блок скрыт по умолчанию

    const validateEmail = (email) => {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return emailRegex.test(email);
    };

    const validateForm = () => {
      let isValid = true;

      if (!form.value.name.trim()) {
        errors.value.name = "Введите ваше имя.";
        isValid = false;
      } else {
        errors.value.name = "";
      }

      if (!form.value.email.trim()) {
        errors.value.email = "Введите ваш email.";
        isValid = false;
      } else if (!validateEmail(form.value.email)) {
        errors.value.email = "Введите корректный email.";
        isValid = false;
      } else {
        errors.value.email = "";
      }

      if (!form.value.masegs.trim()) {
        errors.value.masegs = "Введите ваше сообщение.";
        isValid = false;
      } else {
        errors.value.masegs = "";
      }

      return isValid;
    };

    const submitForm = () => {
      if (validateForm()) {
        console.log("Form Data:", form.value);
        
        // Очищаем форму
        form.value.name = "";
        form.value.email = "";
        form.value.masegs = "";

        // Показываем сообщение об успехе
        isVisible.value = true;
      }
    };

    const hideBlock = () => {
      setTimeout(() => {
        isVisible.value = false;
      }, 200);
    };

    return {
      form,
      errors,
      submitForm,
      isVisible,
      hideBlock,
    };
  },
};
</script>