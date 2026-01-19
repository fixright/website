<script setup>
import { computed } from 'vue'; // Import computed
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

const reviews = [
  {
    rating: "5",
    name: "Sarah J.",
    text: "I hired them to revamp our home office, and I couldn't be happier. They handled everything from installing a new partition wall to laying down new flooring. It was so much easier hiring one team to do it all rather than coordinating different contractors."
  },
  {
    rating: "5",
    name: "Mike T.",
    text: "Had a nightmare with a leaky sink and a clogged drain that I couldn't fix myself. They came out quickly, fixed the plumbing issues, and while they were here, I had them install a new water heater. Knowledgeable, polite, and fair pricing."
  },
  {
    rating: "5",
    name: "Elena R.",
    text: "Our backyard needed serious help. They repaired our fence, cleaned out the gutters, and even built a new garden shed for us. The quality of the outdoor work is top-notch. It feels like we have a whole new garden patio area now."
  }
]

// FIX 1: Duplicate the data 4 times
// This creates a long enough track for wide screens without manual HTML duplication
const allReviews = computed(() => [
  ...reviews,
  ...reviews,
  ...reviews,
  ...reviews
]);
</script>

<template>
  <section id="reviews" class="testimonials">
    <div class="container">
      <div class="title-block">
        <h2>{{ title }}</h2>
        <p class="section-desc">{{ subtitle }}</p>
      </div>

      <div class="slider">
        <div class="slide-track">
          <div v-for="(review, index) in allReviews" :key="index" class="slide">
            <ReviewCard
                :rating="review.rating"
                :name="review.name"
                :text="review.text"
            />
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials {
  padding-bottom: 20px;
  background-color: var(--color-bg-dark);
  overflow: hidden;
}

.container {
  margin: 0 auto;
}

.title-block {
  padding: 70px;
}

.section-desc {
  color: var(--color-text-light);
  margin-bottom: 10px;
}

.slider {
  position: relative;
  width: 100%;
  overflow: hidden;
  padding: 10px 0;
  mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
  -webkit-mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
}

.slide-track {
  display: flex;
  width: max-content;
  gap: 20px;
  animation: scroll 40s linear infinite;
}

.slide-track:hover {
  animation-play-state: paused;
}

.slide {
  width: 350px;
  flex-shrink: 0;
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