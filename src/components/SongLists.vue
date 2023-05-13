<template>
    <div>
      <h2>Song List</h2>
      <ul>
        <li v-for="song in songs" :key="song.songid" @click="selectSong(song)">
          {{ song.title }} - {{ song.artist }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      songs: {
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
  