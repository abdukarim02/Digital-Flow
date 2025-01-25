<template>
  <section class="portfolio">
    <div class="portfolio__content container">
      <h2 class="portfolio__content-title title">Портфолио</h2>
      <div class="portfolio__content_fixed">
        <div class="portfolio__content_fixed-bg" ref="bgContainer">
          <transition name="fade">
            <img
              v-if="showImages.left"
              src="/src/img/portfolio-left.png"
              alt=""
              class="left"
            />
          </transition>
          <transition name="fade">
            <img
              v-if="showImages.top"
              src="/src/img/portfolio-top.png"
              alt=""
              class="top"
            />
          </transition>
          <transition name="fade">
            <img
              v-if="showImages.right"
              src="/src/img/portfolio-right.png"
              alt=""
              class="right"
            />
          </transition>
        </div>
        <a href="#" class="portfolio__content_fixed-btn btn">
          Перейти на сайт
          <svg
            width="8"
            height="13"
            viewBox="0 0 8 13"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M7.33358 6.03176L1.99343 0.691706C1.86992 0.568097 1.70504 0.5 1.52924 0.5C1.35343 0.5 1.18856 0.568097 1.06504 0.691706L0.671779 1.08487C0.415879 1.34107 0.415879 1.75745 0.671779 2.01326L5.15604 6.49751L0.666803 10.9867C0.543292 11.1104 0.475098 11.2751 0.475098 11.4508C0.475098 11.6267 0.543292 11.7915 0.666803 11.9152L1.06007 12.3083C1.18368 12.4319 1.34846 12.5 1.52426 12.5C1.70006 12.5 1.86494 12.4319 1.98845 12.3083L7.33358 6.96336C7.45738 6.83936 7.52538 6.6738 7.52499 6.49781C7.52538 6.32112 7.45738 6.15566 7.33358 6.03176Z"
            />
          </svg>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      showImages: {
        left: false,
        top: false,
        right: false,
      },
    };
  },
  mounted() {
    this.setupIntersectionObserver();
  },
  methods: {
  setupIntersectionObserver() {
    const options = {
      root: null, // viewport
      threshold: 0.1, // элемент виден на 10%
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          // Показать изображения поочередно
          setTimeout(() => {
            this.showImages.left = true;
          }, 100);

          setTimeout(() => {
            this.showImages.top = true;
          }, 500);

          setTimeout(() => {
            this.showImages.right = true;
          }, 1000);
        } else {
          // Скрыть изображения, когда элемент уходит из видимости
          this.showImages = {
            left: false,
            top: false,
            right: false,
          };
        }
      });
    }, options);

    // Проверка наличия элемента
    const bgContainer = this.$refs.bgContainer;
    if (bgContainer) {
      observer.observe(bgContainer);
    } else {
      console.error("bgContainer не найден. Проверьте ref.");
    }
  },
},
};
</script>

<style scoped>
/* Анимация для плавного появления */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}

</style>

  
  
  
  