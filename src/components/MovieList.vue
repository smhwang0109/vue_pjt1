<template>
  <div class="row"> 
    <MovieListItem class="col-3"
      :movie = "movie"
      v-for="movie in movies"
      :key="movie.id"
    />
  </div>
</template>

<script>
import MovieListItem from './MovieListItem.vue'

export default {
  name : 'MovieList',
  components: {
    MovieListItem
  },
  props: {
    movies: Array,
  },
}
</script>

<style>

</style>