<script setup lang="ts">
import { LMap, LTileLayer } from '@maxel01/vue-leaflet'
import { ref, useTemplateRef } from 'vue'

const map = useTemplateRef('map')
const zoom = ref(13)

const onMapReady = () => {
  console.log(map.value.leafletObject)
}
</script>

<template>
  <div class="page-container">
  <div class="map-wrapper" >
    <LMap
    ref="map"
    :zoom="zoom"
    :max-zoom="18"
    :center="[65.02087, 25.47330]"
    @ready="onMapReady"
    >
    <LTileLayer
        url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
        attribution="&amp;copy; <a href=&quot;https://www.openstreetmap.org/&quot;>OpenStreetMap</a> contributors"
        layer-type="base"
        name="OpenStreetMap"
      />
  </LMap>
  </div>
  <div class="buttons">
    <v-btn>Button 1</v-btn>
    <v-btn>Button 2</v-btn>
  </div>
  </div>
</template>

<style lang="css" scoped>
.page-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100%;
  padding: 24px;
  box-sizing: border-box;
  gap: 16px
}

.map-wrapper {
  width: 100%;
  max-width: 98%;
  flex: 1;
  min-height: 0;
  border-radius: 8px;
  overflow: hidden;
}

.buttons {
  display: flex;
  gap: 12px;
  justify-content: center;
  flex-shrink: 0;
}
</style>
