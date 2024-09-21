<template>
  <q-page>
    <div class="q-pa-md q-gutter-sm">
      <q-bar dense class="bg-green text-white">
        <div>Vodafon</div>
        <q-icon name="email" />
        <q-space />
        <q-icon name="bluetooth" />
        <q-icon name="signal_wifi_8_bar" />
        <q-icon name="signal_cellular_4_bar" />
        <div class="gt-xs">99%</div>
        <q-icon name="battery_full" />
        <div>08:48AM</div>
      </q-bar>
    </div>
    <MainCarousel />
  </q-page>
</template>

<script setup>
import MainCarousel from "components/MainCarousel.vue";
defineOptions({
  name: "IndexPage",
});
</script>
