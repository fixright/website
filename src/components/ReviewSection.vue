<script setup>
import ReviewCard from "@/components/ReviewCard.vue";

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
  <section class="testimonials">
    <div class="container">
      <h2>{{ title }}</h2>
      <p class="section-desc">{{ subtitle }}</p>

      <div class="grid">
        <ReviewCard
            rating="5"
            name="Sarah J."
            text="I hired them to revamp our home office, and I couldn't be happier. They handled everything from installing a new partition wall to laying down new flooring. It was so much easier hiring one team to do it all rather than coordinating different contractors. The finish is professional, and they left the place spotless."
        />

        <ReviewCard
            rating="5"
            name="Mike T."
            text="Had a nightmare with a leaky sink and a clogged drain that I couldn't fix myself. They came out quickly, fixed the plumbing issues, and while they were here, I had them install a new water heater. knowledgeable, polite, and very fair pricing. I’ll definitely be calling them back for our bathroom upgrade next month."
        />

        <ReviewCard
            rating="5"
            name="Elena R."
            text="Our backyard needed serious help. They repaired our fence, cleaned out the gutters, and even built a new garden shed for us. The quality of the outdoor work is top-notch. It feels like we have a whole new garden patio area now. Highly recommend for any exterior projects!"
        />


      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials {
  background-color: var(--color-bg-dark);
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
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}


@media (max-width: 768px) {
  .grid {
    grid-template-columns: 1fr;
  }
}

</style>