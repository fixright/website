<script setup>
import { RouterView } from 'vue-router'
import TheFooter from '@/components/TheFooter.vue'
import { useHead } from '@vueuse/head'

useHead({
  title: 'FixRight - Home Repairs & Maintenance Services in Co. Mayo',
  meta: [
    {
      name: 'description',
      content: 'Professional home repair services in County Mayo. Funded by Enterprise Ireland. Experts in plumbing, flooring, wall installation, and garden structures.'
    },
    {
      name: 'geo.region',
      content: 'IE-MO'
    },
    {
      name: 'geo.placename',
      content: 'County Mayo'
    }
  ]
})
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