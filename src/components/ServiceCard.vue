<script setup>
defineProps({
  title: {
    type: String,
    default: 'Default Service'
  },

  description: {
    type: String,
    default: 'Default Description'
  }
})
</script>

<template>
  <div class="card">
    <h3>{{title}}</h3>
    <p class="desc">{{description}}</p>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  padding: 30px;
  text-align: left;
}

.desc {
  color: var(--color-text-light);
}


</style>