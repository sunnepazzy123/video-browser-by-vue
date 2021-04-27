<template>
  <div id="app">
    <SearchBar @termChange="searchItem" />
    <VideoList v-bind:videoList="searchedVideo" />
  </div>
</template>

<script>
import SearchBar from '@/components/SearchBar.vue'
import VideoList from '@/components/VideoList.vue'
import axios from "axios"
const API_KEY = "AIzaSyCRBDkzFwatQJDul-nTtYFka0TTENvLT8A"

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList,
  },

  data(){
    return {
      searchedVideo: []
    }
  },

  methods: {
      async searchItem(searchTerm){
      const config = {
                  key: API_KEY,
                  type: "video",
                  part: "snippet",
                  q: searchTerm
                }
     const res = await axios.get("https://www.googleapis.com/youtube/v3/search", {params: config})
     this.searchedVideo = res.data.items
    //  console.log(res.data.items)
            
    }
  }


}
</script>

<style >
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
