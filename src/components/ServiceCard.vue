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
  background-color: white;
  padding: 30px;
  text-align: left;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  border-radius: var(--border-radius);
}

.desc {
  color: var(--color-text-light);
}


</style>