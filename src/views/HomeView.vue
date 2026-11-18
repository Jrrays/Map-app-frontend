<script setup lang="ts">
import { LMap, LTileLayer } from '@maxel01/vue-leaflet'
import { useTemplateRef } from 'vue'

const map =useTemplateRef('map')

const onMapReady = () => {
  console.log(map.value.leafletObject)
}
</script>

<template>
  <div style="height:100vh; width:100%">
    <LMap
    ref="map"
    :zoom="13"
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
</template>

<style lang="css" scoped></style>
