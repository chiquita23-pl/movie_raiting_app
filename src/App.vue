<script setup>
import { items } from "./movies.json";
import { StarIcon } from "@heroicons/vue/24/solid"


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

<style>

.movie-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.movie h2 {
  text-align: center;
  color: #1e3a8a;
  font-size: 2rem;
  margin: 20px;
}

.movie p {
  text-align: left;
  color: #1e3a8a;
  font-size: 1.2rem;
  margin-bottom: 20px;
}

.stars {
  display: flex;
  gap: 2px;
  color: #facc15;
  margin: 20px;
}

.stars p {
  font-size: 16px;
  margin: 0;
  color: black;
}

.stars svg {
  width: 30px;
  height: auto;
}

.movie-image {
  width: 400px;
  height: auto;
  position: center;
  margin: 0 auto;
  display: block;
}

.movie {
  width: 600px;
  height: auto;
  background-color: lightblue;
  border-radius: 10px;
  margin: 0 auto;
  padding: 20px;
  display: block;
}

.genres {
  display: flex;
  flex-wrap: wrap;
  justify-content: left;
  gap: 6px;
  margin: 12px 0;
}

.genre {
  background-color: pink;
  color: #3730a3;
  padding: 4px 10px;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
}
</style>
