<script setup>
import BaseButton from './BaseButton.vue';

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

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId);
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' });
  } else {
    console.warn(`Element with id "${sectionId}" not found.`);
  }
}
</script>

<template>
  <section class="hero">
    <div class="hero-content">
      <h1>{{title}}</h1>
      <p class="subtitle" v-html="subtitle"></p>

      <div class="actions">
        <BaseButton
            variant="primary"
            @click="scrollToSection('contact')"
        >
          Get started &rarr;
        </BaseButton>

        <BaseButton
            variant="outline"
            @click="scrollToSection('services')"
        >
          Learn more
        </BaseButton>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  overflow: hidden;
  text-align: center;
  padding: 100px 20px;
}

.hero::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

  background-image: url("/images/background.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;

  filter: blur(2px);
  transform: scale(1.1);
  z-index: -2;
}

.hero::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 17, 52, 0.3);
  z-index: -1;
}

.hero-content {
  position: relative;
  z-index: 1;
}

h1 {
  font-size: 32px;
  margin-bottom: 10px;
  color: white;
}

.subtitle {
  color: white;
  opacity: 0.8;
  font-size: 16px;
  margin-bottom: 20px;
}

.actions {
  display: flex;
  gap: 10px;
  justify-content: center;
}

@media (max-width: 530px) {
  h1 {
    font-size: 16px;
  }
  .subtitle {
    font-size: 12px;
  }
}
</style>