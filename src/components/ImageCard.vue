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
  <img :src="icon"  :alt="alt"/>
</template>

<style scoped>

img {
  height: 250px;
  object-fit: contain;
  border-radius: var(--border-radius);
}

@media (max-width: 440px) {
  img {
    height: max-content;
    width: 80%;
  }
}
</style>