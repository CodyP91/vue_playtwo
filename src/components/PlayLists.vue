<template>
  <div>
    <h2>Playlist</h2>
    <ul>
      <li v-for="song in playlist" :key="song.songid">
        <img :src="song.imageurl" alt="Song artwork" />
        <span>{{ song.title }} - {{ song.artist }}</span>
        <button @click="playSong(song)">Play</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'PlayList',
  props: {
    playlist: Array,
  },
  methods: {
    playSong(song) {
      this.$emit('song-played', song);
    },
  },
};
</script>
