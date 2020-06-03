<template>
  <div>
    <div v-if="video" class="mx-5 my-5">
      <div class="details">
        <h4 v-html="video.snippet.title"></h4>
      </div>
      <div class="embed-responsive embed-responsive-16by9">
        <iframe class="embed-responsive-item" :src="videoUrl" allowfullscreen></iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'VideoItemDetail',
  props: {
    video: Object
  },
  computed: {
    videoUrl() {
      return `https://www.youtube.com/embed/${this.video.id.videoId}`;
    }
  }
}
</script>

<style>

</style>