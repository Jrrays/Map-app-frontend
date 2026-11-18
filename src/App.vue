<script setup lang="ts"></script>

<template>
  <v-app>
    <v-app-bar title="Map App">
      <template v-slot:prepend></template>
    </v-app-bar>
    <v-main>
      <router-view v-slot="{ Component }">
        <v-fade-transition hide-on-leave>
          <component :is="Component" />
        </v-fade-transition>
      </router-view>
    </v-main>
  </v-app>
</template>

<style scoped></style>
