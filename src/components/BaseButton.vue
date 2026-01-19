<script setup>
defineProps({
  variant: {
    type: String,
    default: 'primary'
  }
})
</script>

<template>
  <button :class="['btn', variant]">
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  height: 50px;
  width: 150px;
  border-radius: var(--border-radius);
  cursor: pointer;
  transition: all 0.2s;
  font-size: 16px;
  border: 1px solid transparent;
}

.primary {
  background-color: var(--color-primary);
  color: white;
}
.primary:hover {
  background-color: var(--color-primary-hover);
}

.outline {
  background-color: transparent;
  border-color: white;
  color: white;
  opacity: 0.8;
}
.outline:hover {
  opacity: 1;
}
</style>