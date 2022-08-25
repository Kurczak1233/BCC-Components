<script setup>
import UsersGroup from "../icons/UsersGroup.vue";
import PlusIcon from "../icons/PlusIcon.vue";
</script>

<template>
  <div
    class="event-registration-wrapper bg-white rounded-2xl pt-3 flex flex-col mb-6"
  >
    <div class="flex items-center justify-between px-3">
      <div class="font-bold font-serif tracking-wide text-xl">Påskestevnet</div>
      <div class="flex items-center">
        <UsersGroup class="mr-1.5" />
        <span class="font-sans font-semibold text-base">234</span>
      </div>
    </div>
    <div class="text-base font-normal tracking-wider font-sans mt-1.5 px-3">
      Apr 24, 2022 — Apr 26, 2022
    </div>
    <div class="flex mt-4 flex-1 buttons-wrapper">
      <div class="w-6/12 flex flex-col">
        <div class="bg-warmGray h-px w-full flex flex-col"></div>
        <div class="flex items-center justify-evenly flex-1">
          <span
            class="font-normal text-base text-dark-800 uppercase flex text-center"
          >
            Ikke påmeldt
          </span>
        </div>
      </div>
      <div
        class="bg-prime-10 w-6/12 flex items-center justify-evenly rounded-br-2xl"
      >
        <span
          class="font-semibold text-base uppercase text-prime-500 text-center flex items-center"
        >
          Meld på <PlusIcon class="ml-2.5" />
        </span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.buttons-wrapper {
  min-height: 44px;
}
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-prime-500 text-white;
}
</style>
