<script setup>
import "leaflet/dist/leaflet.css";
import { LMap, LTileLayer, LMarker, LPopup } from "@vue-leaflet/vue-leaflet";
import { ref } from "vue";

const zoom = ref(15);
const isInteractive = ref(false);

defineProps({
  title: { type: String, default: 'Default Title' },
  subtitle: { type: String, default: 'Default Subtitle' }
})
</script>

<template>
  <section id="map" class="map">
    <div class="container">
      <h2>{{title}}</h2>
      <p class="section-desc">{{ subtitle }}</p>

      <div class="map-wrapper" @mouseleave="isInteractive = false">

        <div
            v-if="!isInteractive"
            class="click-shield"
            @click="isInteractive = true"
        >
          <span>Click map to interact</span>
        </div>

        <div class="map-vue">
          <l-map
              ref="map"
              v-model:zoom="zoom"
              :center="[50.2631, 19.0221]"
              :use-global-leaflet="false"
          >
            <l-tile-layer
                url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
                layer-type="base"
                name="OpenStreetMap"
            ></l-tile-layer>

            <l-marker :lat-lng="[50.2649, 19.0238]">
              <l-popup> Hello! I am a popup. </l-popup>
            </l-marker>
          </l-map>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.map-wrapper {
  position: relative;
  width: 100%;
  height: 500px;
  border-radius: var(--border-radius);
  overflow: hidden;
}

.map-vue {
  width: 100%;
  height: 100%;
}

.click-shield {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1000;
  background: rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background 0.3s;
}

.click-shield span {
  background: white;
  padding: 8px 16px;
  border-radius: 4px;
  font-weight: bold;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  pointer-events: none;
}

.click-shield:hover {
  background: rgba(0, 0, 0, 0.05);
}

.map {
  padding-bottom: 20px;
  padding-left: 20px;
  padding-right: 20px;
  text-align: center;
}

.container {
  padding: 50px 20px;
  max-width: var(--max-width);
  margin: 0 auto;
}

.section-desc {
  color: var(--color-text-light);
  margin-bottom: 10px;
}
</style>