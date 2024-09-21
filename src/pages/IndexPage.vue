<template>
  <q-page>
    <div class="q-pa-md q-gutter-sm">
      <q-bar dense class="bg-green text-white">
        <div>Vodafone</div>
        <q-icon name="email" />
        <q-space />
        <q-icon name="bluetooth" />
        <q-icon name="signal_wifi_8_bar" />
        <q-icon name="signal_cellular_4_bar" />
        <div class="gt-xs">{{ getRandomIntInclusive(0, 100) }}%</div>
        <q-icon name="battery_full" />
        <div>{{ hour }}:{{ minutes }}:{{ seconds }}</div>
      </q-bar>
    </div>
    <MainCarousel />
  </q-page>
</template>

<script setup>
import { ref } from "vue";
import MainCarousel from "components/MainCarousel.vue";
defineOptions({
  name: "IndexPage",
});

let hour = ref(0);
let minutes = ref(0);
let seconds = ref(0);

function getTime() {
  const date = new Date();
  hour.value = date.getHours();
  minutes.value = date.getMinutes();
  seconds.value = date.getSeconds();
}

getTime();

setInterval(function () {
  getTime();
}, 1000);

function getRandomIntInclusive(min, max) {
  const minCeiled = Math.ceil(min);
  const maxFloored = Math.floor(max);
  return Math.floor(Math.random() * (maxFloored - minCeiled + 1) + minCeiled);
}
</script>
