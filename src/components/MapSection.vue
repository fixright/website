<script setup>
import "leaflet/dist/leaflet.css";
import { LMap, LTileLayer, LMarker, LPopup } from "@vue-leaflet/vue-leaflet";
import { ref } from "vue";

const zoom = ref(13);
const isInteractive = ref(false);

defineProps({
  title: { type: String, default: 'Our Location' },
  subtitle: { type: String, default: 'Find us on the map below' }
})
</script>

<template>
  <section id="location" class="map-section">
    <div class="container">
      <div class="title-block">
        <h2>{{title}}</h2>
        <p class="section-desc">{{ subtitle }}</p>
      </div>

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
              :center="[53.8514, -9.2914]"
              :use-global-leaflet="false"
              :options="{ scrollWheelZoom: isInteractive }"
          >
            <l-tile-layer
                url="https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png"
                attribution='&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors &copy; <a href="https://carto.com/attributions">CARTO</a>'
                layer-type="base"
                name="CartoDB Positron"
            ></l-tile-layer>

            <l-marker :lat-lng="[53.8544, -9.2974]">
              <l-popup>
                <div class="custom-popup">
                  <strong>We are here!</strong><br>
                  Drop by for a coffee.
                </div>
              </l-popup>
            </l-marker>
          </l-map>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.map-section {
  text-align: left;
  overflow: hidden;
}

.title-block {
  padding: 50px;
}

.section-desc {
  margin-top: 10px;
  font-weight: 300;
}

.map-wrapper {
  position: relative;
  width: 100%;
  height: 500px;
  border-radius: 12px;
  overflow: hidden;
}

.map-vue {
  width: 100%;
  height: 100%;
  z-index: 1;
}

.click-shield {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
}


.click-shield span {
  background: #ffffff;
  color: #333333;
  padding: 12px 24px;
  border-radius: 30px;
  font-weight: 600;
  box-shadow: 0 8px 20px rgba(0,0,0,0.12);
  pointer-events: none;
  transition: transform 0.3s ease;
  border: 1px solid #eee;
}

.click-shield:hover {
  background: rgba(255, 255, 255, 0.2);
}

.click-shield:hover span {
  transform: translateY(-2px);
  box-shadow: 0 12px 25px rgba(0,0,0,0.15);
}

\.custom-popup {
  text-align: center;
  color: #333;
}
</style>