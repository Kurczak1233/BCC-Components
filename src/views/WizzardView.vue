<script setup>
import NotificationBar from "../components/Wizzard/NotificationBar.vue";
import EventRegistrationComponent from "../components/Wizzard/EventRegistrationComponent.vue";
</script>

<template>
  <header>
    <NotificationBar />
    <main class="bg-alt-200">
      <div class="h-6 custom-shadow" />
      <div class="px-4">
        <EventRegistrationComponent />
      </div>
    </main>
  </header>
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
