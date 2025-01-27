<template>
    <section class="contacts">
  <div class="contacts__content">
    <div class="contacts__content_form">
      <form id="myForm" class="form" method="post">
        <h2 class="info__title title">Заявка</h2>
        <div class="form__body">
          <div class="form__group">
            <label class="form__group-name" for="name">Ваше имя</label>
            <input 
              class="form__group-text"  
              type="text" 
              id="name" 
              name="name" 
              required 
              aria-required="true" 
              autocomplete="name" 
              aria-describedby="nameError">
            <p id="nameError" class="error-message" role="alert"></p>       
          </div>
          <div class="form__group">
            <label class="form__group-name" for="email">Ваш Email</label>
            <input 
              class="form__group-text" 
              type="email" 
              id="email" 
              name="email" 
              required 
              aria-required="true" 
              autocomplete="email" 
              aria-describedby="emailError">
            <p id="emailError" class="error-message" role="alert"></p>     
          </div>
          <div class="form__group">
            <label class="form__group-name" for="masegs">Ваше сообщение</label>
            <textarea 
              class="form__group-text" 
              id="masegs" 
              name="masegs" 
              required 
              aria-required="true" 
              aria-describedby="masegsError"></textarea>    
            <p id="masegsError" class="error-message" role="alert"></p>     
          </div>
          <button id="submit" class="form-submit btn">
            ОТПРАВИТЬ 
            <svg width="8" height="13" viewBox="0 0 8 13" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M7.33352 6.03176L1.99337 0.691706C1.86985 0.568097 1.70498 0.5 1.52917 0.5C1.35337 0.5 1.18849 0.568097 1.06498 0.691706L0.671718 1.08487C0.415818 1.34107 0.415818 1.75745 0.671718 2.01326L5.15597 6.49751L0.666742 10.9867C0.543231 11.1104 0.475037 11.2751 0.475037 11.4508C0.475037 11.6267 0.543231 11.7915 0.666742 11.9152L1.06001 12.3083C1.18362 12.4319 1.3484 12.5 1.5242 12.5C1.7 12.5 1.86488 12.4319 1.98839 12.3083L7.33352 6.96336C7.45732 6.83936 7.52532 6.6738 7.52493 6.49781C7.52532 6.32112 7.45732 6.15566 7.33352 6.03176Z"/>
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
</template>
