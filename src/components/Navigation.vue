<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const isMenuOpen = ref(false);
const isFixed = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const handleScroll = () => {
  if (window.scrollY > 0) {
    isFixed.value = true;
  } else {
    isFixed.value = false;
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <header :class="{'fixed': isFixed}" class="header">
    <div class="header__content container">
      <a href="#" class="header__content_logo">
        <img src="/src/img/logo.svg" alt="Logo" class="header__content_logo-img">
        <img src="/src/img/logo-white.svg" alt="Logo" class="header__content_logo-img-white">
      </a>
      <div class="header__content_menu">
        <button class="header__content_menu-burger" @click="toggleMenu">
          <span></span>
          <span></span>
          <span></span>
        </button>
        <div class="header__content_menu-body" v-if="isMenuOpen">
            <button class="body__close" @click="toggleMenu">
              <svg width="21" height="21" viewBox="0 0 21 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M10.5002 8.61902L2.43418 0.553274C1.90952 0.0283702 1.06122 0.02837 0.536559 0.553274C0.0119009 1.07793 0.011901 1.92624 0.536559 2.4509L8.60254 10.5169L0.53656 18.5826C0.0119017 19.1075 0.0119018 19.9556 0.53656 20.4803C1.06122 21.0052 1.90952 21.0052 2.43418 20.4803L10.5002 12.4145L18.5661 20.4803C19.0908 21.0052 19.9391 21.0052 20.4638 20.4803C20.7255 20.2188 20.8569 19.875 20.8569 19.5314C20.8569 19.1879 20.7255 18.8444 20.4638 18.5826L12.3978 10.5169L20.4638 2.4509C20.7255 2.18918 20.8569 1.84564 20.8569 1.50209C20.8569 1.15854 20.7255 0.814994 20.4637 0.553277C19.9391 0.0283728 19.0908 0.0283726 18.5661 0.553277L10.5002 8.61902Z" fill="white" fill-opacity="0.3" />
              </svg>
            </button>
          <div class="body__menu">     
            <ul class="body__menu_item">
              <li class="body__menu_item-list"><a href="#" class="body__menu_item-list-link">Главная</a></li>
              <li class="body__menu_item-list"><a href="#" class="body__menu_item-list-link">О компании</a></li>
              <li class="body__menu_item-list"><a href="#" class="body__menu_item-list-link">Портфолио</a></li>
              <li class="body__menu_item-list"><a href="#" class="body__menu_item-list-link">Что мы предлагаем</a></li>
              <li class="body__menu_item-list"><a href="#" class="body__menu_item-list-link">Специальное предложение</a></li>
            </ul>
            <button class="body__menu_btn">Оставить заявку
              <svg width="8" height="12" viewBox="0 0 8 12" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M7.33358 5.53176L1.99343 0.191706C1.86992 0.068097 1.70504 0 1.52924 0C1.35343 0 1.18856 0.068097 1.06504 0.191706L0.671779 0.584873C0.415879 0.841066 0.415879 1.25745 0.671779 1.51326L5.15604 5.99751L0.666803 10.4867C0.543292 10.6104 0.475098 10.7751 0.475098 10.9508C0.475098 11.1267 0.543292 11.2915 0.666803 11.4152L1.06007 11.8083C1.18368 11.9319 1.34846 12 1.52426 12C1.70006 12 1.86494 11.9319 1.98845 11.8083L7.33358 6.46336C7.45738 6.33936 7.52538 6.1738 7.52499 5.99781C7.52538 5.82112 7.45738 5.65566 7.33358 5.53176Z" fill="white" />
              </svg>
            </button>
            <div class="body__menu_social">
              <a href="#" class="body__menu_social-link">
                <svg width="20" height="18" viewBox="0 0 20 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M7.8474 11.6506L7.51657 16.304C7.9899 16.304 8.1949 16.1006 8.44073 15.8565L10.6599 13.7356L15.2582 17.1031C16.1016 17.5731 16.6957 17.3256 16.9232 16.3273L19.9416 2.18398L19.9424 2.18314C20.2099 0.936476 19.4916 0.448976 18.6699 0.754809L0.928237 7.54731C-0.282596 8.01731 -0.264262 8.69231 0.722404 8.99814L5.25823 10.409L15.7941 3.81648C16.2899 3.48814 16.7407 3.66981 16.3699 3.99814L7.8474 11.6506Z" fill="#17181C" />
                </svg>
              </a>
              <a href="#" class="body__menu_social-link">
                <svg width="20" height="18" viewBox="0 0 20 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M7.8474 11.6506L7.51657 16.304C7.9899 16.304 8.1949 16.1006 8.44073 15.8565L10.6599 13.7356L15.2582 17.1031C16.1016 17.5731 16.6957 17.3256 16.9232 16.3273L19.9416 2.18398L19.9424 2.18314C20.2099 0.936476 19.4916 0.448976 18.6699 0.754809L0.928237 7.54731C-0.282596 8.01731 -0.264262 8.69231 0.722404 8.99814L5.25823 10.409L15.7941 3.81648C16.2899 3.48814 16.7407 3.66981 16.3699 3.99814L7.8474 11.6506Z" fill="#17181C" />
                </svg>
              </a>
              <a href="#" class="body__menu_social-link">
                <svg width="20" height="18" viewBox="0 0 20 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M7.8474 11.6506L7.51657 16.304C7.9899 16.304 8.1949 16.1006 8.44073 15.8565L10.6599 13.7356L15.2582 17.1031C16.1016 17.5731 16.6957 17.3256 16.9232 16.3273L19.9416 2.18398L19.9424 2.18314C20.2099 0.936476 19.4916 0.448976 18.6699 0.754809L0.928237 7.54731C-0.282596 8.01731 -0.264262 8.69231 0.722404 8.99814L5.25823 10.409L15.7941 3.81648C16.2899 3.48814 16.7407 3.66981 16.3699 3.99814L7.8474 11.6506Z" fill="#17181C" />
                </svg>
              </a>
              <a href="#" class="body__menu_social-link">
                <svg width="20" height="18" viewBox="0 0 20 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M7.8474 11.6506L7.51657 16.304C7.9899 16.304 8.1949 16.1006 8.44073 15.8565L10.6599 13.7356L15.2582 17.1031C16.1016 17.5731 16.6957 17.3256 16.9232 16.3273L19.9416 2.18398L19.9424 2.18314C20.2099 0.936476 19.4916 0.448976 18.6699 0.754809L0.928237 7.54731C-0.282596 8.01731 -0.264262 8.69231 0.722404 8.99814L5.25823 10.409L15.7941 3.81648C16.2899 3.48814 16.7407 3.66981 16.3699 3.99814L7.8474 11.6506Z" fill="#17181C" />
                </svg>
              </a>
              <a href="#" class="body__menu_social-link">
                <svg width="20" height="18" viewBox="0 0 20 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M7.8474 11.6506L7.51657 16.304C7.9899 16.304 8.1949 16.1006 8.44073 15.8565L10.6599 13.7356L15.2582 17.1031C16.1016 17.5731 16.6957 17.3256 16.9232 16.3273L19.9416 2.18398L19.9424 2.18314C20.2099 0.936476 19.4916 0.448976 18.6699 0.754809L0.928237 7.54731C-0.282596 8.01731 -0.264262 8.69231 0.722404 8.99814L5.25823 10.409L15.7941 3.81648C16.2899 3.48814 16.7407 3.66981 16.3699 3.99814L7.8474 11.6506Z" fill="#17181C" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>
<style scoped>
.header {
    width: 100%;
    transition: all 0.3s ease-in;
}
.header.fixed {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  background: #191a1e;
}
.header.fixed .header__content_logo .header__content_logo-img {
  display: none;
}
.header.fixed .header__content_logo .header__content_logo-img-white {
  display: block;
}
.header.fixed .header__content_menu span {
  background: #fff;
}
</style>