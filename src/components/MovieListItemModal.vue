<template>
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">{{ movie.title }}</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <img class="img-fluid" :src="movie.backdrop_url">
        <hr>
        <span class="badge badge-pill badge-success">{{ movie.user_rating }}</span>
        <p>{{ movie.overview }}</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name : 'MovieListItemModal',
  props : {
    movie: Object
  }
}
</script>

<style>
</style>