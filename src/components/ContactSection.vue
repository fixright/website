<script setup>
import ContactInformation from "@/components/ContactInformation.vue";
import ContactForm from "@/components/ContactForm.vue";

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
  <section id="contact" class="contact">
    <div class="container">
      <div class="title-block">
        <h2>{{ title }}</h2>
        <p class="section-desc">{{ subtitle }}</p>
      </div>

      <div class="content-wrapper">

        <ContactInformation/>
        <ContactForm/>

      </div>
    </div>
  </section>
</template>

<style scoped>

.title-block
{
  margin-bottom: 50px;
}

.contact {
  padding: 4rem 1rem;
  background: white;
}

.container {
  max-width: 900px;
  margin: 0 auto;
}

.section-desc {
  color: var(--color-text-light);
  margin-bottom: 10px;
}


.content-wrapper {
  display: flex;
  gap: 4rem;
  justify-content: center;
}

@media (max-width: 768px) {
  .content-wrapper {
    flex-direction: column-reverse;
    gap: 2rem;
  }
}
</style>