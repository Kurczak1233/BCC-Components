<script setup>
import NotificationBar from "../components/Wizzard/NotificationBar.vue";
import EventRegistrationComponent from "../components/Wizzard/EventRegistrationComponent.vue";
</script>

<template>
  <div class="h-full flex flex-col">
    <NotificationBar />
    <main class="bg-alt-200 flex-1">
      <div class="h-6 custom-shadow" />
      <div class="px-4">
        <EventRegistrationComponent />
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
