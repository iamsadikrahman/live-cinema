<template>
  <h1 class="text-3xl text-bold" v-if="isLoading">Loading</h1>
  <div class="flex space-x-5 flex-wrap" v-else>
    <MovieCard v-for="movie in moviesList" :key="movie.id" :movie="movie" />
  </div>
  <div></div>
  <h1>This is Movies Page</h1>
</template>

<script setup>
import { reactive, ref, onMounted } from "vue";

import MovieCard from "../components/MovieCard.vue";

let moviesList = reactive([]);

let isLoading = ref(true);

onMounted(() => {
  fetch("http://localhost:8000/movies/")
    .then((response) => response.json())
    .then((apiMovies) => {
      moviesList = apiMovies;
      console.log(moviesList);
      isLoading.value = false;
    })
    .catch((error) => {
      console.error("Error Fetching", error);

      isLoading.value = false;
    });
});
</script>

<style scoped></style>
