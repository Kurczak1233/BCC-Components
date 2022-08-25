<script setup>
import EventRegistrationComponent from "../components/Wizzard/EventRegistrationComponent.vue";
import BCCGrenland from "../components/Wizzard/Headers/BCC-Grenland.vue";
import EventsHeader from "../components/Wizzard/Headers/EventsHeader.vue";
import FellesOrIndividuell from "../components/Wizzard/Headers/FellesOrIndividuell.vue";
import NotificationBar from "../components/Wizzard/Headers/NotificationBar.vue";

import { ref } from "vue";

const confirmedNotification = ref(false);

const mockedHeaderData = {
  componentTitle: "Felles",
  isGroup: true,
  checked: true,
  possibleItems: 0,
  maxItems: 9,
  extraInfo: "Folg 2",
};

const mockedHeaderDataInactive = {
  componentTitle: "Individuell",
  isGroup: false,
  checked: false,
  possibleItems: 0,
  maxItems: 1,
};

// const mockedEventData = {
//   registerd: false,
// };

// const mockedEventDataInactive = {
// registerd: true,
// };
</script>

<template>
  <div class="h-full flex flex-col">
    <EventsHeader />
    <NotificationBar
      v-if="!confirmedNotification"
      @confirmedNotification="(value) => (confirmedNotification = value)"
    />
    <div>
      <BCCGrenland />
      <div class="py-4 flex items-center">
        <FellesOrIndividuell v-bind="mockedHeaderData" />
        <FellesOrIndividuell v-bind="mockedHeaderDataInactive" />
      </div>
    </div>
    <main class="bg-alt-200 flex-1">
      <div class="px-4">
        <div v-for="n in 10" :key="n"><EventRegistrationComponent /></div>
      </div>
    </main>
  </div>
</template>
