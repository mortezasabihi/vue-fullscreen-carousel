<template>
  <div class="carousel">
    <carousel-slide
      v-for="(slide, index) in slides"
      :key="index"
      :slide="slide"
    />
  </div>
</template>

<script>
import CarouselSlide from "@/components/Carousel/CarouselSlide";

export default {
  name: "Carousel",
  components: {
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
    };
  },
  watch: {
    current(value) {
      if (value === this.slides.length - 1) {
        this.timer = setTimeout(() => (this.current = 0), this.delay);
      }
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
  },
  created() {
    this.changeSlide();
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
