<script setup>
import FellesOrIndividuell from "./FellesOrIndividuell.vue";

const mockedDataActive = {
  componentTitle: "Felles",
  isGroup: true,
  checked: true,
  possibleItems: 0,
  maxItems: 9,
  extraInfo: "Folg 2",
};

const mockedData = {
  componentTitle: "Individuell",
  isGroup: false,
  checked: false,
  possibleItems: 0,
  maxItems: 1,
};
</script>

<template>
  <div class="p-4 flex items-center">
    <!-- <div class="flex items-center justify-between mb-4">
      <span class="font-semibold text-base font-sans">
        Velg type påmelding
      </span>
      <span class="text-small-medium font-medium text-prime-500 font-sans">
        Fjern filter
      </span>
    </div> -->
    <FellesOrIndividuell v-bind="mockedDataActive" />
    <FellesOrIndividuell v-bind="mockedData" />
  </div>
</template>
<!-- I could not find an appropriate color for secondary lighter -->
<style scoped>
.text-small-medium {
  font-size: 15px;
  line-height: 20px;
}
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-prime-500 text-white;
}
</style>
