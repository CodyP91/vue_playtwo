<template>
  <div>
    <h2>Now Playing</h2>
    <div v-if="currentSong">
      <img :src="currentSong.imageurl" alt="Song artwork" />
      <p>{{ currentSong.title }} - {{ currentSong.artist }}</p>
    </div>
    <p v-else>No song is playing...</p>cd 
  </div>
</template>

<script>
export default {
  name: 'NowPlaying',
  props: {
    currentSong: Object,
  },
};
</script>
