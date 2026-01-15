<script setup>
defineProps({
  name: {
    type: String,
    default: 'Default Name'
  },
  text: {
    type: String,
    default: 'Default Text'
  },
  rating: {
    type: Number,
    default: 5
  }
})
</script>

<template>
  <div class="review-card">
    <div class="stars">
      <span
          v-for="i in 5"
          :key="i"
          class="star"
          :class="{ 'filled': i <= rating }"
      >
        ★
      </span>
    </div>

    <h3>{{ name }}</h3>
    <p class="desc">{{ text }}</p>
  </div>
</template>

<style scoped>


.review-card {
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  padding: 30px;
  text-align: left;
}


.desc {
  color: var(--color-text-light);
}

.stars {
  margin-bottom: 5px;
  user-select: none;
}

.star {
  color: #d1d5db;
  font-size: 16px;
  margin-right: 2px;
}

.star.filled {
  color: #fbbf24;
}

</style>