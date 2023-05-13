<template>
  <div>
    <song-list :songs="songs" @song-selected="addSongToPlaylist"></song-list>
    <play-list :playlist="playlist" @song-selected="selectSong"></play-list>
    <now-playing :song="nowPlaying"></now-playing>
  </div>
</template>

<script>
import SongList from '@/components/SongLists.vue';
import PlayList from '@/components/PlayLists.vue';
import NowPlaying from '@/components/NowPlaying.vue';

export default {
  components: {
    SongList,
    PlayList,
    NowPlaying
  },
  data() {
    return {
      songs: [
        {
          title: 'Song 1',
          artist: 'Artist 1',
          songid: '1',
          imageurl: 'https://placehold.it/200x200'
        },
        {
          title: 'Song 2',
          artist: 'Artist 2',
          songid: '2',
          imageurl: 'https://placehold.it/200x200'
        },
        {
          title: 'Song 3',
          artist: 'Artist 3',
          songid: '3',
          imageurl: 'https://placehold.it/200x200'
        }
      ],
      playlist: [],
      nowPlaying: null
    };
  },
  methods: {
    addSongToPlaylist(song) {
      this.playlist.push(song);
    },
    selectSong(song) {
      this.nowPlaying = song;
    }
  }
};
</script>
