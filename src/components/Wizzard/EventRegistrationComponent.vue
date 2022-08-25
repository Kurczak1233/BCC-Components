<script setup>
import GrayUser from "../icons/GrayUser.vue";
</script>

<template>
  <div class="event-registration-wrapper bg-white rounded-2xl pt-3 px-3">
    <div class="flex items-center justify-between">
      <div class="font-bold font-serif tracking-wide text-xl">Påskestevnet</div>
      <div class="flex items-center">
        <GrayUser class="mr-1.5" />
        <span class="font-sans font-semibold text-base">234</span>
      </div>
    </div>
    <div class="text-base font-normal tracking-wider font-sans">
      Apr 24, 2022 — Apr 26, 2022
    </div>
    <div>
      <div>Ikke påmeldt</div>
      <div>Meld på</div>
    </div>
  </div>
</template>

<style scoped>
.event-registration-wrapper {
  height: 130px;
}
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-prime-500 text-white;
}
</style>
