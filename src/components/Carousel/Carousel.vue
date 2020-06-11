<template>
  <div class="carousel">
    <carousel-loading v-if="loading" />

    <template v-else>
      <carousel-slide
        v-for="(slide, index) in slides"
        :key="index"
        :slide="slide"
      />
    </template>
  </div>
</template>

<script>
import CarouselLoading from "@/components/Carousel/CarouselLoading";
import CarouselSlide from "@/components/Carousel/CarouselSlide";

export default {
  name: "Carousel",
  components: {
    CarouselLoading,
    CarouselSlide,
  },
  props: {
    /**
     * Slides
     * @type { array }
     */
    slides: {
      required: true,
      type: Array,
    },
    /**
     * Delay
     * @type { number }
     */
    delay: {
      required: false,
      type: Number,
      default: () => 3000,
    },
  },
  data() {
    return {
      current: 0,
      interval: null,
      timer: null,
      loading: true,
    };
  },
  watch: {
    current(value) {
      if (value === this.slides.length - 1) {
        this.timer = setTimeout(() => (this.current = 0), this.delay);
      }
    },
    loading: {
      handler(value) {
        !value && this.changeSlide();
      },
      immediate: true,
    },
  },
  methods: {
    /**
     * Change slide
     * @function
     * @returns { void }
     */
    changeSlide() {
      this.interval = setInterval(() => {
        if (this.current < this.slides.length - 1) this.current += 1;
      }, this.delay);
    },
    /**
     * Load images
     * @function
     * @returns { void }
     */
    loadImages() {
      let imageLoaded = 0;
      const IMAGES = [];
      this.slides.forEach((slide) => IMAGES.push(slide.image));

      for (const IMAGE of IMAGES) {
        const IMG = new Image();
        IMG.src = IMAGE;

        IMG.onload = () => {
          imageLoaded++;

          if (imageLoaded === IMAGES.length) this.loading = false;
        };
      }
    },
  },
  created() {
    this.loadImages();
  },
  beforeDestroy() {
    clearInterval(this.interval);
    clearTimeout(this.timer);
  },
};
</script>

<style scoped>
.carousel {
  height: 100vh;
  display: flex;
  overflow: hidden;
  user-select: none;
}
</style>
