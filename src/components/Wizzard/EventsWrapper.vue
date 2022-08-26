<script setup>
import EventRegistrationComponent from "./EventRegistrationComponent.vue";
const mockedEventDataNotRegistered = {
  registered: false,
  availableToRegister: true,
  numberOfPeopleOnEvent: 21,
};
</script>

<template>
  <div
    class="py-4 px-2 font-sans tracking-wide font-semibold text-base secondary-light mx-2 my-6 rounded-3xl"
  >
    <div
      class="font-sans tracking-wide font-semibold text-base flex items-center justify-evenly mb-2"
    >
      Du kan velge én av disse
    </div>
    <div v-for="n in 3" :key="n">
      <EventRegistrationComponent
        v-bind="mockedEventDataNotRegistered"
        :noMargin="n === 3"
      />
    </div>
  </div>
</template>

<!-- I could not find an appropriate color for secondary light -->
<style scoped>
.buttons-wrapper {
  min-height: 44px;
}
.secondary-light {
  background-color: #e2e7cd;
}
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-prime-500 text-white;
}
</style>
