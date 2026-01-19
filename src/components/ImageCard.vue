<script setup>
defineProps({
  icon: {
    type: String,
  },
  alt: {
    type: String,
  }
})
</script>

<template>
  <div class="image-container">
    <img :src="icon" :alt="alt"/>
  </div>
</template>

<style scoped>
.image-container {
  filter: drop-shadow(0px 4px 10px rgba(0, 0, 0, 0.2));
}

img {
  height: 250px;
  width: 100%;
  object-fit: cover;
  clip-path: polygon(20% 0, 100% 0, 80% 100%, 0% 100%);
  border-radius: 0;
  display: block;
}

@media (max-width: 440px) {
  img {
    height: auto;
    min-height: 200px;
    clip-path: polygon(10% 0, 100% 0, 90% 100%, 0% 100%);
  }
}
</style>