<script setup></script>

<template>
  <header class="pt-4 pb-3 pr-7 pl-6 font-sans">
    <div class="font-medium uppercase text-sm opacity-90 tracking-wide">
      STEG 1
    </div>
    <div class="mt-2 text-xl font-medium">
      Meld deg på til inkluderte stevner
    </div>
    <div class="mt-2.5 font-normal opacity-80">
      Dette er stevner som BCC Grenland har inkludert i budsjett for
      givertjeneste.
    </div>
    <div class="mt-2 flex justify-between items-center">
      <div class="font-medium text-small-medium">Påmeldt 0 av 9</div>
      <div class="btn btn-blue">Neste</div>
    </div>
  </header>
</template>

<style scoped>
@tailwind base;
@tailwind components;
@tailwind utilities;
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
