<template>
  <div class="slider">
    <div class="slides" ref="slides">
      <slot></slot>
    </div>
    <div class="pagination-container"> 
      <button class="slider-button prev" @click="prevSlide" :disabled="isPrevDisabled">
        <img src="assets/img/left.svg" alt="Previous" />
      </button>
      <div class="pagination">
        <button v-for="index in totalSlides" :key="index" class="pagination__dot"
          :class="{ active: currentIndex === index - 1 }" @click="goToSlide(index - 1)"></button>
      </div>
      <button class="slider-button next" @click="nextSlide" :disabled="isNextDisabled">
        <img src="assets/img/right.svg" alt="Next" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
    };
  },
  computed: {
    totalSlides() {
      return this.$slots.default ? this.$slots.default().length : 0;
    },
    isPrevDisabled() {
      return this.currentIndex === 0;
    },
    isNextDisabled() {
      return this.currentIndex === this.totalSlides - 1;
    },
  },
  methods: {
    updateSlidePosition() {
      const slideWidth = this.$refs.slides.clientWidth;
      this.$refs.slides.style.transform = `translateX(-${this.currentIndex * slideWidth}px)`;
    },
    nextSlide() {
      if (this.currentIndex < this.totalSlides - 1) {
        this.currentIndex += 1;
      }
      this.updateSlidePosition();
    },
    prevSlide() {
      if (this.currentIndex > 0) {
        this.currentIndex -= 1;
      } else {
        this.currentIndex = this.totalSlides - 1;
      }
      this.updateSlidePosition();
    },
    goToSlide(index) {
      this.currentIndex = index;
      this.updateSlidePosition();
    },
  },
  mounted() {
    this.updateSlidePosition();
  },
};
</script>

<style lang="scss" scoped>
.slider {
  display: none;
}

@media screen and (max-width: 375px) {
  .slider {
    display: block;
    width: 100%;
    overflow: hidden;
    position: relative;
    top: 92px;


    .slides {
      display: flex;
      transition: transform 0.5s ease-in-out;
      width: 100%;
    }

    ::v-deep>* {
      flex: 0 0 100%;
    }
  }

  .pagination-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 178px;
    margin: 28px auto;
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
    width: 36px;
    height: 36px;
    background-color: $textcolor-dark;
    border: none;
    border-radius: 50px;
    cursor: pointer;

    &:hover {
      background-color: $color-light;
      border: none;
    }

    &:disabled {
      background-color: #d3d3d3;
      cursor: not-allowed;
    }
  }
}
</style>
