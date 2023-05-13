<template>
  <div id="app">
    <h1>Music Playlist</h1>
    <SongList :songs="songs" @song-selected="addToPlaylist" />
    <PlayList :playlist="playlist" @song-played="playSong" />
    <NowPlaying :currentSong="currentSong" />
  </div>
</template>

<script>
import SongList from './components/SongList.vue';
import PlayList from './components/PlayList.vue';
import NowPlaying from './components/NowPlaying.vue';

export default {
  name: 'App',
  components: {
    SongList,
    PlayList,
    NowPlaying,
  },
  data() {
    return {
      songs: [
      ],
      playlist: [],
      currentSong: null,
    };
  },
  methods: {
    addToPlaylist(song) {
      this.playlist.push(song);
    },
    playSong(song) {
      this.currentSong = song;
    },
  },
};
</script>

<style>

</style>
