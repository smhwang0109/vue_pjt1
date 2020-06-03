<template>
  <div class="container">
    <VideoSearch @input-change="onInputChange" />
    <VideoItem :videos="videos" />
  </div>
</template>

<script>
import axios from "axios";

import VideoSearch from "../components/VideoSearch.vue";
import VideoItem from "../components/VideoItem.vue";

const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY;
const API_URL = "https://www.googleapis.com/youtube/v3/search";

export default {
  name: "VideoView",
  components: { VideoSearch, VideoItem },
  data() {
    return {
      inputValue: "",
      videos: []
    };
  },
  methods: {
    onInputChange(inputText) {
      this.inputValue = inputText;

      axios
        .get(API_URL, {
          params: {
            key: API_KEY,
            part: "snippet",
            type: "video",
            q: `${this.inputValue} trailer`,
            maxResults: 3
          }
        })
        .then(res => {
          this.videos = res.data.items
          })
        .catch(err => console.error(err));
    }
  }
};
</script>
<style scoped>

</style>