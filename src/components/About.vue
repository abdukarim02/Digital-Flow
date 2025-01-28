<template>
    <section class="about">
        <div class="about__company">
             <Swiper :slides-per-view="1" :pagination="{ clickable: true }" class="about__company_swiper">
                <SwiperSlide>
                    <div class="about__company_swiper-bg">
                        <img src="/src/img/about-bg.png" alt="">
                    </div>
                    <div class="about__company_swiper_content">
                        <div class="about__company_swiper_content-info">
                        <h2 class="about__company_swiper_content-info-title title">О компании</h2>
                        <p class="about__company_swiper_content-info-text text">Мы диджитал агентство занимаемся полным циклом продвижения компаний в интернете.</p>
                        <p class="about__company_swiper_content-info-text text">Мы диджитал агентство занимаемся полным циклом продвижения компаний в интернете.</p>
                        <p class="about__company_swiper_content-info-text text">Мы диджитал агентство занимаемся полным циклом продвижения компаний в интернете.</p>
                        </div>        
                    </div>
                </SwiperSlide>
                <SwiperSlide>
                    <div class="about__company_swiper-bg">
                        <img src="/src/img/about-bg.png" alt="">
                    </div>
                    <div class="about__company_swiper_content">
                        <div class="about__company_swiper_content-info">
                        <h2 class="about__company_swiper_content-info-title title">О компании</h2>
                        <p class="about__company_swiper_content-info-text text">Мы диджитал агентство занимаемся полным циклом продвижения компаний в интернете.</p>
                        <p class="about__company_swiper_content-info-text text">Мы диджитал агентство занимаемся полным циклом продвижения компаний в интернете.</p>
                        <p class="about__company_swiper_content-info-text text">Мы диджитал агентство занимаемся полным циклом продвижения компаний в интернете.</p>
                        </div>        
                    </div>
                </SwiperSlide>
            </Swiper> 
        </div>
    </section>
</template>
<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/pagination';
//   export default {
//         components: {
//           Swiper,
//           SwiperSlide,
//         },
//         setup() {
//           const onSwiper = (swiper) => {
//             console.log(swiper);
//           };
//           const onSlideChange = () => {
//             console.log('slide change');
//           };
//           return {
//             onSwiper,
//             onSlideChange,
//             modules: [Navigation, Pagination, Scrollbar, A11y],
//           };
//         },
//       };
</script>