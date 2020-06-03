<template>
  <div>
    <div class="card" >
      <img :src="movie.poster_url" class="card-img-top" alt="포스터 이미지">
      <div class="card-body">
        <h5 class="card-title">{{ movie.title }}</h5>
        <button type="button" class="btn btn-warning" data-toggle="modal" :data-target="'#movie'+movie.id">
          영화정보 상세보기
        </button>
        <div class="modal fade" :id="'movie'+movie.id" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <MovieListItemModal
            :movie="movie"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MovieListItemModal from '../components/MovieListItemModal.vue'

export default {
  name: 'MovieListItem',
  components: {
    MovieListItemModal,
  },
  props: {
    movie: Object
  }
}
</script>

<style>

</style>