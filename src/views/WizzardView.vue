<script setup>
import EventRegistrationComponent from "../components/Wizzard/EventRegistrationComponent.vue";
import BCCGrenland from "../components/Wizzard/Headers/BCC-Grenland.vue";
import EventsHeader from "../components/Wizzard/Headers/EventsHeader.vue";
import FellesOrIndividuell from "../components/Wizzard/Headers/FellesOrIndividuell.vue";
import NotificationBar from "../components/Wizzard/Headers/NotificationBar.vue";

import { ref } from "vue";
import EventsWrapper from "../components/Wizzard/EventsWrapper.vue";

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

const mockedEventData = {
  registered: true,
  availableToRegister: true,
  numberOfPeopleOnEvent: 123,
};

const mockedEventDataInactive = {
  registered: false,
  availableToRegister: false,
  numberOfPeopleOnEvent: 32,
};
const mockedEventDataNotRegistered = {
  registered: false,
  availableToRegister: true,
  numberOfPeopleOnEvent: 21,
};
</script>

<template>
  <div class="h-full flex flex-col">
    <div
      :class="
        confirmedNotification
          ? `${'flex flex-col z-40'}`
          : `w-screen h-screen fixed flex flex-col z-40`
      "
    >
      <EventsHeader />
      <NotificationBar
        @confirmedNotification="(value) => (confirmedNotification = value)"
        v-if="!confirmedNotification"
      />
      <div
        class="bg-gray flex-1 bg-black z-20 opacity-60 custom-top-offset"
        v-if="!confirmedNotification"
      />
    </div>
    <div>
      <BCCGrenland />
      <div class="py-4 flex items-center custom-shadow z-20">
        <FellesOrIndividuell v-bind="mockedHeaderData" />
        <FellesOrIndividuell v-bind="mockedHeaderDataInactive" />
      </div>
    </div>
    <main
      :class="
        confirmedNotification
          ? `${'bg-alt-200 flex-1 overflow-auto pt-4'}`
          : `bg-alt-200 flex-1 overflow-hidden pt-4`
      "
    >
      <div class="px-4">
        <div v-for="n in 4" :key="n">
          <EventRegistrationComponent v-bind="mockedEventData" />
        </div>
        <div v-for="n in 3" :key="n">
          <EventRegistrationComponent v-bind="mockedEventDataNotRegistered" />
        </div>
        <div v-for="n in 3" :key="n">
          <EventRegistrationComponent v-bind="mockedEventDataInactive" />
        </div>
      </div>
      <EventsWrapper />
    </main>
  </div>
</template>

<style scoped>
.custom-top-offset {
  top: 250px;
}
.custom-shadow {
  box-shadow: 0px 24px 20px -4px rgb(0 0 0 / 10%);
}
</style>
