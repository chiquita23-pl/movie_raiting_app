<script setup>
import { items } from "./movies.json";
import { StarIcon } from "@heroicons/vue/24/solid"
import "./movie_list.css";

</script>

<template>
  <!-- This is where your template goes	-->
   <div class="movie-list">
    <div class="movie" v-for="item in items" :key="item.id">
      <img class="movie-image" :src="item.image" :alt="item.name" />
      <h2>{{ item.name }}</h2>
      <div class="genres">
        <span class="genre" v-for="genre in item.genres" :key="genre">{{ genre }}</span>
      </div>
      <p>{{ item.description }}</p>

      <div class="stars" >
        <p> Raiting: ({{ item.rating }} / 5)</p>
        <StarIcon  v-for="n in item.rating" :key="n" />
      </div>
    </div>
  </div>
</template>
