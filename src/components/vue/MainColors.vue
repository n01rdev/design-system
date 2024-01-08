<template>
  <div class="flex flex-col space-y-12">
    <div v-for="name in colorNames" :key="name">
      <h3 class="capitalize">{{ name }}</h3>
      <div class="grid grid-cols-5 md:grid-cols-10">
        <div v-for="color in COLORS[name]" :key="color">
        <div class="mb-4"></div>
          <div
              class="h-12 transition-all"
              :style="`background: ${color.value}`"
          ></div>
          <div
              class="text-sm flex flex-col text-center font-mono text-slate-500"
          >
            <div class="mb-4"></div>
            <span>{{ color.name }}</span>
            <span class="uppercase text-xs">{{ color.value }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import {COLORS} from "../../config/design.config.ts";

const colorNames = Object.keys(COLORS);
</script>