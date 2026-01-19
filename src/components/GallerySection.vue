<script setup>
import { ref, computed } from 'vue';

defineProps({
  title: {
    type: String,
    default: 'Default Title'
  },
  subtitle: {
    type: String,
    default: 'Default Subtitle'
  }
})

const images = ref([
  { src: '/website/images/image1.jpg', alt: 'Image 1' },
  { src: '/website/images/image2.jpg', alt: 'Image 2' },
  { src: '/website/images/image3.jpg', alt: 'Image 3' },
]);

// FIX: Duplicate the array 4 times.
// This ensures the track is long enough for even the widest monitors.
const allImages = computed(() => [
  ...images.value,
  ...images.value,
  ...images.value,
  ...images.value
]);
</script>

<template>
  <section id="gallery" class="gallery">
    <div class="container">
      <div class="title">
        <h2>{{ title }}</h2>
        <p class="section-desc">{{ subtitle }}</p>
      </div>

      <div class="slider-window">
        <div class="slider-track">
          <div v-for="(img, index) in allImages" :key="index" class="slanted-card">
            <img :src="img.src" :alt="img.alt" />
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.gallery {
  text-align: left;
  overflow: hidden;
}

.title {
  padding: 50px;
}

.container {
  max-width: 100%;
  margin: 0 auto;
}

.section-desc {
  color: #666;
}

.slider-window {
  width: 100%;
  overflow: hidden;
  mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
  -webkit-mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
}

.slider-track {
  display: flex;
  width: max-content;
  animation: scroll 20s linear infinite;
}

.slider-track:hover {
  animation-play-state: paused;
}

.slanted-card {
  width: 400px;
  height: 250px;
  position: relative;
  overflow: hidden;
  transform: skewX(-10deg);
  border-right: 4px solid white;
  background: #ccc;
  backface-visibility: hidden;
  margin-right: -1px;
}

.slanted-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transform: skewX(10deg) scale(1.2);
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-25%);
  }
}
</style>