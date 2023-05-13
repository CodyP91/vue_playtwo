<template>
    <div>
      <h2>Play List</h2>
      <ul>
        <li v-for="song in playlist" :key="song.songid" @click="selectSong(song)">
          {{ song.title }} - {{ song.artist }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      playlist: {
        type: Array,
        required: true
      }
    },
    methods: {
      selectSong(song) {
        this.$emit('song-selected', song);
      }
    }
  };
  </script>
  