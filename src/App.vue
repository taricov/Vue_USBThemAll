<script setup>
import { onMounted } from "vue";

onMounted(() => {
  const script = document.createElement("script");

  script.src = "https://buttons.github.io/buttons.js";
  script.async = true;

  document.body.appendChild(script);
});
</script>

<template>
  <div class="h-screen bg-gray-800 text-white">
    <header class="py-16"></header>

    <div class="flex items-center justify-center gap-16">body for now</div>
  </div>
</template>
