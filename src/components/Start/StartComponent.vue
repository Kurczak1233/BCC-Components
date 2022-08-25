<script setup>
import GreenCalendarSvg from "../icons/GreenCalendar.vue";
</script>

<template>
  <div>
    <div class="flex justify-evenly items-center">
      <div
        class="flex justify-evenly items-center w-14 h-14 bg-prime-10 rounded-full"
      >
        <GreenCalendarSvg />
      </div>
    </div>
    <div class="flex justify-evenly">
      <span class="text-lg font-semibold mt-6 text-center font-sans"
        >Velkommen til årspåmelding</span
      >
    </div>
    <div class="flex justify-evenly">
      <span class="text-lg text-base mt-2 text-center font-sans opacity-60">
        Påmeld deg til stevner og camps for 2023 ved hjelp av enkle steg
      </span>
    </div>
    <div class="flex justify-evenly">
      <RouterLink to="/wizzard" class="btn btn-blue mt-8 w-10/12 text-center">
        <span class="font-sans text-lg font-semibold">Start</span>
      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
@tailwind base;
@tailwind components;
@tailwind utilities;
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-prime-500 text-white;
}
</style>
