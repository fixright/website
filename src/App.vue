<script setup>
import { RouterView } from 'vue-router'
import TheFooter from '@/components/TheFooter.vue'
</script>

<template>
  <div class="app-layout">
    <RouterView />

    <TheFooter
        title="FixRight"
        subtitle="A small call-out home repairs company funded by Enterprise Ireland."
    />
  </div>
</template>

<style>
</style>