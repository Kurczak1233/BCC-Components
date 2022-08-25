<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div>
    <RouterLink to="/"></RouterLink>
    <RouterLink to="/about"></RouterLink>
  </div>

  <RouterView />
</template>
