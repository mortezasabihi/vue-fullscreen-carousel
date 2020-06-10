<template>
  <div :style="transform" class="carousel__slide">
    <img :src="slide.image" class="slide__image" />
    <div class="slide__content">
      <div class="slide__title">{{ slide.title }}</div>
      <div class="slide__description">{{ slide.description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CarouselSlide",
  props: {
    /**
     * Slide
     * @type { object }
     */
    slide: {
      required: true,
      type: Object,
    },
  },
  computed: {
    /**
     * Transform style
     * @function
     * @returns { object }
     */
    transform() {
      return {
        transform: `translateX(${this.$parent.current * -100}%)`,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.carousel {
  &__slide {
    position: relative;
    flex: 0 0 100%;
    transition: all 0.5s;
  }
}

.slide {
  &__image {
    width: 100%;
    height: 100%;
    max-width: 100%;
    object-fit: cover;
  }

  &__content {
    position: absolute;
    bottom: 60px;
    left: 60px;
    right: 60px;
    padding: 25px 40px;
    background-color: rgba(0, 0, 0, 0.5);
    color: #fff;
  }

  &__title {
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 20px;
  }

  &__description {
    line-height: 24px;
    font-size: 17px;
  }
}
</style>
