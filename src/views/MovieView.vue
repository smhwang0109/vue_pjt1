<template>
  <div>
    <h2>나만의 무비 컬렉션</h2>
    <div v-if="movies" class="container">
      <MovieList :movies="movies"/>
    </div>
    <div v-else>
      <button @click="onButtonClick" class="btn btn-primary call">영화 가져오기</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import MovieList from '../components/MovieList.vue'

export default {
  name: 'MovieView',
  components : {
    MovieList,
  },
  data() {
    return {
      movies: false
    }
  },
  methods: {
    onButtonClick() {
      axios.get('https://www.json-generator.com/api/json/get/ceNyuXZmwi?indent=2')
        .then(
          res => {
            this.movies = res.data
            console.log(res.data)

          })
        .catch(err => console.error(err));
    }
  }
}
</script>

<style>

</style>