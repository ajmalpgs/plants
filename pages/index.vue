<template>
  <div class="home-page">
    <swiper
      :slides-per-view="1"
      :space-between="30"
      loop="true"
      autoplay
      :autoplay="{ delay: 3000 }"
      pagination
      navigation
    >
      <swiper-slide v-for="(slide, index) in slides" :key="index" class="slide">
        <img :src="slide.image" :alt="'Garden Slide ' + (index + 1)" class="slide-image" />
        <div class="quote-box">
          <p class="quote">{{ slide.quote }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import SwiperCore, { Autoplay, Pagination, Navigation } from "swiper";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";

SwiperCore.use([Autoplay, Pagination, Navigation]);

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      slides: [
        {
          image: "images/g1.jpg",
          quote: "Gardening adds years to your life and life to your years.",
        },
        {
          image: "images/g2.jpg",
          quote: "To plant a garden is to believe in tomorrow.",
        },
        {
          image: "images/g3.jpg",
          quote: "Gardening is the purest of human pleasures. - Francis Bacon",
        },
        {
          image: "images/g4.jpg",
          quote: "A garden requires patient labor and attention. Plants do not grow merely to satisfy ambitions or to fulfill good intentions. They thrive because someone expended effort on them.",
        },
        {
          image: "images/g5.jpg",
          quote: "Gardens are not made by singing 'Oh, how beautiful,' and sitting in the shade.",
        },
        {
          image: "images/g6.jpg",
          quote: "The glory of gardening: hands in the dirt, head in the sun, heart with nature. To nurture a garden is to feed not just the body, but the soul.",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Ensure the page fits within the viewport */
.home-page {
  height: 100vh; /* Full height of the viewport */
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden; /* Disable scrolling */
  background-color: #f8f9fa; /* Optional: Background color */
}

.swiper {
  width: 90%;
  height: 85%;
}

.slide {
  position: relative;
  height: 100%;
}

.slide-image {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensure the image covers the slide without distortion */
}

.quote-box {
  position: absolute;
  top: 50%; /* Center vertically */
  left: 50%; /* Center horizontally */
  transform: translate(-50%, -50%); /* Adjust for centering */
  background: rgba(0, 0, 0, 0.6); /* Semi-transparent background */
  color: #fff;
  padding: 20px 30px;
  border-radius: 8px;
  text-align: center;
  max-width: 80%;
}

.quote {
  font-size: 1.2rem;
  font-style: italic;
}
</style>