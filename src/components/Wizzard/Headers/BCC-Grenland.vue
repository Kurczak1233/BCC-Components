<script setup>
import BCCLogo from "../../icons/BCCLogo.vue";
import BCCGrenland from "../../icons/BCCGrenland.vue";
</script>

<template>
  <div class="p-4 bg-alt-200 flex items-center justify-center">
    <BCCLogo class="mr-2.5 color-primary" />
    <BCCGrenland />
  </div>
</template>
<style scoped>
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
