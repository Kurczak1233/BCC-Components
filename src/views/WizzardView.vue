<script setup>
import EventRegistrationComponent from "../components/Wizzard/EventRegistrationComponent.vue";
import BCCGrenland from "../components/Wizzard/Headers/BCC-Grenland.vue";
import EventsHeader from "../components/Wizzard/Headers/EventsHeader.vue";
import FellesOrIndividuell from "../components/Wizzard/Headers/FellesOrIndividuell.vue";
import NotificationBar from "../components/Wizzard/Headers/NotificationBar.vue";

import { ref } from "vue";
import EventsWrapper from "../components/Wizzard/EventsWrapper.vue";

const confirmedNotification = ref(false);
const scrollingMenu = ref(null);
const fixedFiltrations = ref(false);

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

const handleScroll = () => {
  if (scrollingMenu.value.scrollTop > 64) {
    fixedFiltrations.value = true;
  } else {
    fixedFiltrations.value = false;
  }
};
</script>

<template>
  <div class="h-full flex flex-col">
    <EventsHeader />
    <div
      :class="
        confirmedNotification
          ? `${'flex flex-col z-40 '}`
          : `w-screen h-screen fixed flex flex-col z-40`
      "
      v-if="!confirmedNotification"
    >
      <NotificationBar
        @confirmedNotification="(value) => (confirmedNotification = value)"
      />
      <div class="bg-gray flex-1 bg-black z-20 opacity-60 custom-top-offset" />
    </div>
    <main
      @scroll="handleScroll"
      ref="scrollingMenu"
      :class="
        confirmedNotification
          ? `${'bg-alt-200 flex-1 overflow-auto custom-event-header-offset relative'}`
          : `bg-alt-200 flex-1 overflow-hidden custom-event-header-offset relative`
      "
    >
      <BCCGrenland
        :class="fixedFiltrations ? `${'custom-margin-bottom'}` : ``"
      />
      <div
        :class="
          fixedFiltrations
            ? `${'py-4 flex items-center custom-shadow z-20 bg-white w-full fixed custom-events-top-offset'}`
            : `py-4 flex items-center custom-shadow z-20 bg-white w-full`
        "
      >
        <FellesOrIndividuell v-bind="mockedHeaderData" />
        <FellesOrIndividuell v-bind="mockedHeaderDataInactive" />
      </div>
      <div class="px-4 mt-4">
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
  top: 120px;
}
.custom-margin-bottom {
  margin-top: 120px;
}
.custom-events-top-offset {
  top: 60px;
}
.custom-event-header-offset {
  margin-top: 60px;
}
.custom-shadow {
  box-shadow: 0px 24px 20px 5px rgb(0 0 0 / 10%);
}
</style>
