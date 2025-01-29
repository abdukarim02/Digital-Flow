<script setup>
import Navigation from './components/Navigation.vue';
import MainSection from './components/MainSection.vue';
import About from './components/About.vue';
import Portfolio from './components/Portfolio.vue';
import Services from './components/Services.vue';
import Advantages from './components/Advantages.vue';
import Contacts from './components/Contacts.vue';
import ConfirmationModal from './components/ConfirmationModal.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <Navigation />
  <section class="wrapper">
    <MainSection /> 
  </section>
  <About/>
  <Portfolio/>
  <Services/>
  <Advantages/>
  <Contacts/>
  <ConfirmationModal />
  <Footer/>
</template>

