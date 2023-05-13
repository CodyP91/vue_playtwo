<template>
    <div>
      <h2>Now Playing</h2>
      <div v-if="song">
        <h3>{{ song.title }} - {{ song.artist }}</h3>
        <img :src="song.imageurl" :alt="song.title" width="200">
      </div>
      <div v-else>
        <p>Please select a song to play.</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      song: {
        type: Object,
        required: false,
        default: null
      }
    }
  };
  </script>
  