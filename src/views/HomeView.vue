<template>
  <main>
    <HeroSection
        title="FixRight Home Repairs Company"
        subtitle="A small call-out home repairs company funded by Enterprise Ireland. <br> With experience over 2 years."
    />
    <ServicesSection
        title="Our Services"
        subtitle="Comprehensive solutions"
    />
    <ReviewSection
        title="What Our Clients Say"
        subtitle="Don't just take our word for it - hear from our satisfied clients"
    />
    <ContactSection
        title="Get In Touch"
        subtitle="Have a question? We'd love to hear from you."
    />
  </main>
</template>

<script setup>
import HeroSection from '@/components/HeroSection.vue'
import ServicesSection from '@/components/ServicesSection.vue'
import ReviewSection from '@/components/ReviewSection.vue'
import ContactSection from '@/components/ContactSection.vue'
</script>