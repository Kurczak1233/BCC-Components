<script setup>
import { ref } from "vue";
const items = ref([
  { text: "Foo" },
  { text: "Bar" },
  { text: "Påskestevnet" },
  { text: "B Påskestevnet Påskestevnet" },
]);
</script>

<template>
  <div class="mt-7 pl-7 pr-7">
    <div class="flex justify-evenly">
      <div class="w-10/12">
        <span class="text-lg font-semibold mt-6 font-sans">Felles</span>
        <div v-for="item in items" :key="item.text">
          <span class="font-sans text-lg font-normal">{{ item.text }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>
