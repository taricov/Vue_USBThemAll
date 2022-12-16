<script setup>
// import { onMounted } from "vue";

// onMounted(() => {
//   const script = document.createElement("script");

//   script.src = "https://buttons.github.io/buttons.js";
//   script.async = true;

// document.body.appendChild(script);
// });
import navDrawer from "./components/navDrawer.vue";
import { ref } from "vue";

const theme = ref("light");

const themeOnClick = () => {
  theme.value = theme.value === "light" ? "dark" : "light";
};

const appDrawerOnClick = () => {
  let drawer;
};
</script>

<template>
  <v-app class="h-screen text-white" :theme="theme">
    <v-app-bar title="" :elevation="3">
      <v-app-bar-nav-icon @click="appDrawerOnClick" />
      <v-spacer></v-spacer>
      <template v-slot:append>
        <v-btn icon="mdi-heart"></v-btn>

        <v-btn icon="mdi-magnify"></v-btn>

        <v-btn icon="mdi-dots-vertical"></v-btn>
        <v-btn
          :prepend-icon="
            theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'
          "
          @click="themeOnClick"
          >{{ theme }}</v-btn
        >
      </template>
    </v-app-bar>

    <!-- <v-navigation-drawer>
      <div>
        <header class="py-16"></header>

        <div class="flex items-center justify-center gap-16">
          Items goes here
        </div>
      </div>
    </v-navigation-drawer> -->

    <v-main class="flex items-center justify-center gap-16"></v-main>
    <navDrawer
      class="flex items-center justify-center gap-16"
      v-model="drawer"
    />
  </v-app>
</template>
