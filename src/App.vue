<script setup>
import Navigation from './components/Navigation.vue';
import MainSection from './components/MainSection.vue';
import About from './components/About.vue';
import Portfolio from './components/Portfolio.vue';
import Services from './components/Services.vue';


</script>

<template>
  <Navigation />
  <section class="wrapper">
    <MainSection /> 
  </section>
  <About/>
  <Portfolio/>
  <Services/>
  <section class="advantages">
    <div class="advantages__content container">
      <div class="advantages__content_header">
        <div class="advantages__content_header-bg">
          <img src="/src/img/remove-bg.png" alt="">
        </div>
        <div class="advantages__content_header-bg">
          <img src="/src/img/remove-bg.png" alt="">
        </div>
        <div class="advantages__content_header-bg">
          <img src="/src/img/remove-bg.png" alt="">
        </div>
      </div>
      <h2 class="advantages__content-title title">Наши преимущества</h2>
      <div class="advantages__content_wrap">
        <div class="advantages__content_wrap-flex">
          <div class="advantages__flex">
            <div class="advantages__flex-bg">
              <img src="/src/img/advantages-logo-1.svg" alt="">
            </div>
            <div class="advantages__flex-info">
              <p>Сделаем адаптивный дизайн, под любой вид устройств</p>
            </div>
          </div>
        </div>
        <div class="advantages__content_wrap-flex">
          <div class="advantages__flex">
            <div class="advantages__flex-bg">
              <img src="/src/img/advantages-logo-1.svg" alt="">
            </div>
            <div class="advantages__flex-info">
              <p>Сделаем адаптивный дизайн, под любой вид устройств</p>
            </div>
          </div>
        </div>
        <div class="advantages__content_wrap-flex">
          <div class="advantages__flex">
            <div class="advantages__flex-bg">
              <img src="/src/img/advantages-logo-1.svg" alt="">
            </div>
            <div class="advantages__flex-info">
              <p>Сделаем адаптивный дизайн, под любой вид устройств</p>
            </div>
          </div>
        </div>
        <div class="advantages__content_wrap-flex">
          <div class="advantages__flex">
            <div class="advantages__flex-bg">
              <img src="/src/img/advantages-logo-1.svg" alt="">
            </div>
            <div class="advantages__flex-info">
              <p>Сделаем адаптивный дизайн, под любой вид устройств</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

