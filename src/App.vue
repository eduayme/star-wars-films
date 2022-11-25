<template>
  <main>
    <Header />
    <Loader v-if="!films.length" />
    <div v-else class="films-content">
      <Card
        v-for="(film, index) in films"
        :key="film.episode_id"
        :data="film"
        :image-id="index+1"
      />
    </div>
    <Footer />
  </main>
</template>

<script setup>
import Header from "./components/Header.vue"
import Loader from "./components/Loader.vue"
import Card from "./components/Card.vue"
import Footer from "./components/Footer.vue"
import { ref, onMounted } from 'vue'

const API_URL = "https://swapi.dev/api/films/"
const films = ref([]);

const fetchMoviesJSON = async() => {
  const response = await fetch(API_URL);
  const movies = await response.json();
  return movies;
}

onMounted(async () =>{
  fetchMoviesJSON().then(movies => {
    films.value = movies.results
  });
})
</script>

<style scoped>
.films-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin: 20px 10%;
}
</style>