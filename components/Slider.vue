<template>
  <div>
    <slot></slot>
  </div>
  <div class="pagination-container">
    <button class="slider-button prev" @click="prevSlide">
      <img src="assets/img/left.svg" alt="Previous" />
    </button>
    <div class="pagination">
      <button
        v-for="index in totalSlides"
        :key="index"
        class="pagination__dot"
        :class="{ active: currentIndex === index - 1 }"
        @click="goToSlide(index - 1)"
      ></button>
    </div>
    <button class="slider-button next" @click="nextSlide">
      <img src="assets/img/right.svg" alt="Next" />
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      itemsPerPage: 1,
      currentIndex: 0,
    };
  },
  computed: {
    totalSlides() {
      return this.$slots.default.length;
    },
  },
  methods: {
    updateSlidePosition() {
      const slideWidth = 100 / this.totalSlides;
      this.$refs.slides.style.transform = `translateX(-${
        this.currentIndex * slideWidth
      }%)`;
    },
    nextSlide() {
      if (this.currentIndex < this.totalSlides - 1) {
        this.currentIndex += 1;
      } else {
        this.currentIndex = 0;
      }
    },
    prevSlide() {
      if (this.currentIndex > 0) {
        this.currentIndex -= 1;
      } else {
        this.currentIndex = this.totalSlides - 1;
      }
    },
    goToSlide(index) {
      this.currentIndex = index;
    },
  },
  mounted() {
    const slide = this.$refs.slide;
    if (slide && slide.style) {
      this.updateSlidePosition();
    }
  },
};
</script>

<style lang="scss" scoped>
.pagination-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 178px;
  margin: 0 auto;
}
.pagination {
  display: flex;
}

.pagination__dot {
  width: 10px;
  height: 10px;
  border: none;
  border-radius: 50%;
  background: #d9d9d9;
  margin: 0 6px;
  cursor: pointer;
}

.pagination__dot.active {
  background: $textcolor-dark;
}

.slider-button {
  width: 44px;
  height: 44px;
  background-color: $textcolor-dark;
  border: none;
  border-radius: 50px;
  cursor: pointer;
}

.slider-button.prev {
    background: #D9D9D9;
}
</style>
