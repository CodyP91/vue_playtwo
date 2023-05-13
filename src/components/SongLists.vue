<template>
  <div>
    <h2>Song List</h2>
    <ul>
      <li v-for="song in songs" :key="song.songid">
        <img :src="song.imageurl" alt="Song artwork" />
        <span>{{ song.title }} - {{ song.artist }}</span>
        <button @click="selectSong(song)">Add to Playlist</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SongList',
  props: {
    songs: Array,
  },
  methods: {
    selectSong(song) {
      this.$emit('song-selected', song);
    },
  },
};
</script>
