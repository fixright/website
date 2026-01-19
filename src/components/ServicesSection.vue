<script setup>
import ServiceCard from "@/components/ServiceCard.vue";

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
  <section id="services" class="services">
    <div class="container">
      <div class="title-block">
        <h2>{{ title }}</h2>
        <p class="section-desc">{{ subtitle }}</p>
      </div>

      <div class="grid">
        <ServiceCard
            title="Wall Services"
            description="Complete wall installation for new room layouts, plus professional wallpaper installation to add character and style to any space."
        />

        <ServiceCard
            title="Flooring Solutions"
            description="Expert installation of new flooring, along with tile removal, precise repairs for cracked tiles, and general floor restoration to keep your surfaces looking new."
        />

        <ServiceCard
            title="Doors & Windows"
            description="Full-service installation and repair for standard and sliding doors. We also handle window repairs, apply window tinting for privacy/efficiency, and install custom blinds."
        />

        <ServiceCard
            title="Furniture & Cabinetry"
            description="Hassle-free assembly and installation of furniture and kitchen/storage cabinetry. We also perform repairs on existing joinery."
        />

        <ServiceCard
            title="Fixtures & Mounting"
            description="Secure wall mounting for TVs, floating shelves, artwork, and mirrors, ensuring safety and perfect alignment."
        />

        <ServiceCard
            title="Plumbing Repairs"
            description="Quick fixes for leaky sinks, dripping faucets, and clogged drains to prevent water damage."
        />

        <ServiceCard
            title="Installations & Upgrades"
            description="Installation of water heaters, toilet repairs, bath refurbishment, and general hardware upgrades to modernize your kitchen or bathroom."
        />

        <ServiceCard
            title="Lighting & Fans"
            description="Repair and installation of indoor/outdoor lighting fixtures and ceiling fans."
        />

        <ServiceCard
            title="Smart Home & Utilities"
            description="Installation of modern thermostats, smart doorbells, and general electrical repairs to keep your home connected and safe."
        />

        <ServiceCard
            title="Structural Maintenance"
            description="Gutter cleaning and repair to protect your roof, plus repairs for driveways and paved patios."
        />

        <ServiceCard
            title="Fencing & Enclosures"
            description="Installation of new fences for privacy and security, as well as repairs to existing fence lines."
        />

        <ServiceCard
            title="Garden Structures"
            description="Assembly and construction of garden sheds, laying of garden patios, and general outdoor revamping to transform your backyard into a usable living space."
        />
      </div>

    </div>
  </section>
</template>

<style scoped>
.services {
  padding-bottom: 20px;
  padding-left: 20px;
  padding-right: 20px;
  background-color: var(--color-bg-dark);

}

.title-block {
  padding: 50px;
}

.container {
  margin: 0 auto;
}

.section-desc {
  color: var(--color-text-light);
}

.grid {
  padding-left: 50px;
  padding-right: 50px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}


@media (max-width: 1080px) {
  .grid {
    grid-template-columns: 1fr;
  }
}
</style>