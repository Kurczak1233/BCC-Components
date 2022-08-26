<script setup>
const emit = defineEmits(["confirmedNotification"]);

const clickOnConfirmButton = () => {
  emit("confirmedNotification", true);
};
</script>

<template>
  <div
    class="pt-4 pb-3 pr-7 pl-6 font-sans secondary-lighter fixed z-10 custom-top-length custom-shadow w-full"
  >
    <div class="font-medium uppercase text-sm opacity-90 tracking-wide">
      STEG 1
    </div>
    <div class="mt-2 text-xl font-medium">
      Meld deg på til inkluderte stevner
    </div>
    <div class="mt-2.5 font-normal opacity-60">
      Dette er stevner som BCC Grenland har inkludert i budsjett for
      givertjeneste.
    </div>
    <div class="mt-2 flex justify-between items-center">
      <div class="font-medium text-small-medium font-sans">Påmeldt 0 av 9</div>
      <div @click="clickOnConfirmButton" class="btn btn-blue">Neste</div>
    </div>
  </div>
</template>
<!-- I could not find an appropriate color for secondary lighter -->
<style scoped>
.custom-shadow {
  box-shadow: 0px 12px 6px -4px rgba(0, 0, 0, 0.25);
}
.secondary-lighter {
  background: #e9edd9;
}
.custom-top-length {
  top: 60px;
}
.text-small-medium {
  font-size: 15px;
}
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-prime-500 text-white;
}
</style>
