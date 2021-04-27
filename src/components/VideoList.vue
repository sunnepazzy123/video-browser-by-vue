<template>
  <div>
    <h1>Video List Component</h1>
    <ul>
      <VideoListItem v-for="video in videoList" :key="video.etag" :video="video" />
    </ul>
  
  </div>
</template>

<script>
import VideoListItem from "@/components/VideoListItem"
export default {
  props: {
    videoList: Array,
  },

  components: {
    VideoListItem,

  },

  data(){
    return {

    }
  },

  methods: {

  }

}
</script>

<style>

</style>