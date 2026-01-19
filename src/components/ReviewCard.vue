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
  background-color: white;
  padding: 30px;
  text-align: left;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  border-radius: var(--border-radius);
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