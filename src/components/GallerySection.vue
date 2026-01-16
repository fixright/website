<script setup>
import ImageCard from "@/components/ImageCard.vue";
import Icon from "@/components/Icon.vue";

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
</script>

<template>
  <section id="gallery" class="gallery">
    <div class="container">
      <h2>{{title}}</h2>
      <p class="section-desc">{{ subtitle }}</p>

      <div class="grid">

        <ImageCard
            icon="/website/images/image1.jpg"
            alt="Image1"
        />

        <ImageCard
            icon="/website/images/image2.jpg"
            alt="Image2"
        />

        <ImageCard
            icon="/website/images/image3.jpg"
            alt="Image3"
        />

      </div>

    </div>
  </section>
</template>

<style scoped>
.gallery {
  padding-bottom: 20px;
  padding-left: 20px;
  padding-right: 20px;
  text-align: center;
}

.container {
  padding: 50px 20px;
  max-width: var(--max-width);
  margin: 0 auto;
}

.section-desc {
  color: var(--color-text-light);
  margin-bottom: 10px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, auto);
  justify-content: center;
  gap: 10px;
}

@media (max-width: 1200px) {
  .grid {
    grid-template-columns: repeat(2, auto);
  }
}

@media (max-width: 820px) {
  .grid {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}
</style>