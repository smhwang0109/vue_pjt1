<template>
  <div>
    <ul>
      <VideoItemDetail v-for="video in videos" :key="video.etag" :video="video" />
    </ul>
  </div>
</template>

<script>
import VideoItemDetail from "./VideoItemDetail.vue";

export default {
  name: "VideoItem",
  props: {
    videos: Array
  },
  components: {
    VideoItemDetail
  }
};
</script>

<style>
</style>