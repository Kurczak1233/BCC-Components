<script setup>
// import NotificationBar from "../components/Wizzard/Headers/NotificationBar.vue";
import EventRegistrationComponent from "../components/Wizzard/EventRegistrationComponent.vue";
import BCCGrenland from "../components/Wizzard/Headers/BCC-Grenland.vue";
import PameldingComponent from "../components/Wizzard/Headers/PameldingComponent.vue";
import EventsHeader from "../components/Wizzard/Headers/EventsHeader.vue";
</script>

<template>
  <div class="h-full flex flex-col">
    <EventsHeader />
    <!-- <NotificationBar /> -->
    <BCCGrenland />
    <PameldingComponent />
    <main class="bg-alt-200 flex-1">
      <div class="h-6 custom-shadow" />
      <div class="px-4">
        <div v-for="n in 10" :key="n"><EventRegistrationComponent /></div>
      </div>
    </main>
  </div>
</template>

<style scoped>
@tailwind base;
@tailwind components;
@tailwind utilities;

.custom-shadow {
  background: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0.1) 0%,
    rgba(0, 0, 0, 0) 100%
  );
}
</style>
