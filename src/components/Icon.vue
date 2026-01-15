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
  <div class="content">
    <img :src="icon"  :alt="alt"/>
  </div>
</template>

<style scoped>

.content {
  display: flex;
  height: 50px;
  width: 50px;
  align-items: center;
  justify-content: center;
  border-radius: var(--border-radius);
  background-color: var(--color-bg-dark);
}

img {
  height: 25px;
  width: 25px;
  object-fit: contain;
}
</style>