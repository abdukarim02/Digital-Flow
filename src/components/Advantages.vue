<template>
    <section class="advantages">
      <div class="advantages__content container">
        <div class="advantages__content_header">
          <div 
            v-for="(bg, index) in headers" 
            :key="index" 
            :class="['advantages__content_header-bg', { 'is-visible': visibleImages.includes(index) }]">
            <img src="/src/img/remove-bg.png" alt="">
          </div>
        </div>
        <h2 class="advantages__content-title title">Наши преимущества</h2>
        <div class="advantages__content_wrap">
          <div 
            v-for="(item, index) in advantages" 
            :key="index" 
            :class="['advantages__content_wrap-flex', { 'is-visible': visibleImages.includes(index + headers.length) }]">
            <div class="advantages__flex">
              <div class="advantages__flex-bg">
                <img src="/src/img/advantages-logo-1.svg" alt="">
              </div>
              <div class="advantages__flex-info">
                <p>{{ item.text }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>
  
<script>
  export default {
    data() {
      return {
        headers: [1, 2, 3], // Заглушки для фоновых изображений
        advantages: [
          { text: 'Сделаем адаптивный дизайн, под любой вид устройств' },
          { text: 'Установим на сайт счетчики аналитики и настроим возможность отслеживать результаты прямо с вашего мобильного телефона' },
          { text: 'Настроим все возможные способы обратной связи. Заявки на почту, подключим онлайн консультанта, настроим телефонный звон с сайта, подключим Whatsapp к сайту' },
          { text: 'Установим на сайт счетчики аналитики и настроим возможность отслеживать результаты прямо с вашего мобильного телефона' }
        ],
        visibleImages: [],
        imagesRevealed: false // Флаг для предотвращения повторного вызова
      };
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
      window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
      handleScroll() {
        const section = this.$el;
        const sectionTop = section.getBoundingClientRect().top;
        const windowHeight = window.innerHeight;
  
        // Проверка: если флаг уже установлен, не запускаем анимацию снова
        if (sectionTop < windowHeight - 100 && !this.imagesRevealed) {
          this.imagesRevealed = true; // Устанавливаем флаг, чтобы анимация не запускалась снова
          this.revealImages();
        }
      },
      revealImages() {
        const totalImages = this.headers.length + this.advantages.length;
  
        // Если все изображения уже видимы, прерываем выполнение
        if (this.visibleImages.length === totalImages) return;
  
        let index = 0;
        const interval = setInterval(() => {
          if (index < totalImages) {
            this.visibleImages.push(index);
            index++;
          } else {
            clearInterval(interval);
          }
        }, 500); // Задержка между появлениями в миллисекундах
      }
    }
  };
</script>
  
<style scoped>
  .advantages__content_header-bg,
  .advantages__content_wrap-flex {
    opacity: 0;
    transform: translateY(-20px);
    transition: all 0.5s ease;
  }
  
  .advantages__content_header-bg.is-visible,
  .advantages__content_wrap-flex.is-visible {
    opacity: 1;
    transform: translateY(0);
  }
</style>
  
  