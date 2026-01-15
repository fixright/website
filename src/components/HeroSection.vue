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
    <h1>{{title}}</h1>
    <p class="subtitle" v-html="subtitle"></p>

    <div class="actions">
      <BaseButton
          variant="primary"
          @click="scrollToSection('services')"
      >
        Get started &rarr;
      </BaseButton>

      <BaseButton
          variant="outline"
          @click="scrollToSection('contact')"
      >
        Learn more
      </BaseButton>
    </div>
  </section>
</template>

<style scoped>

.hero {
  background-color: var(--color-bg-dark);
  text-align: center;
  padding: 100px 20px;
}

h1 {
  font-size: 32px;
  margin-bottom: 10px;
}

.subtitle {
  color: var(--color-text-light);
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