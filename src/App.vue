<script setup>
import { RouterLink, RouterView } from "vue-router";
import FlowBite from "./components/FlowBite.vue";
</script>

<template>
  <h1>This is App</h1>

  <nav class="flex justify-center items-center gap-5 text-3xl">
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/about">About</RouterLink>
    <RouterLink to="/movies">Movies</RouterLink>
  </nav>

  <RouterView />
  <FlowBite></FlowBite>
</template>

<style scoped></style>
