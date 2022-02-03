<template>
  <v-card class="rounded-lg" color="#0F0A1E" dark>
    <v-row class="row">
      <v-col cols="12" sm="12">
        <v-toolbar color="rgba(0,0,0,0)" flat dark class="py-4">
          <v-toolbar-title class="mt-n10">
            <span class="caption">Top Releases</span>
          </v-toolbar-title>
        </v-toolbar>
        <v-list
          subheader
          two-line
          class=""
          flat
          color="rgba(0,0,0,0)"
          dark
          v-for="(song, i) in songs"
          :key="i"
        >
          <v-list-item class="py-n8">
            <span class="mr-2 caption">{{ i + 1 }}</span>
            <v-list-item-avatar class="mr-2" rounded height="80px" width="80px">
              <v-img  :src="song.img" size="80" />
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title
                >{{ song.title }} by ({{ song.artist }})</v-list-item-title
              >
              <v-list-item-subtitle class="caption">{{
                song.listner
              }}</v-list-item-subtitle>
              <v-rating
                v-model="song.rated"
                color="yellow darken-3"
                background-color="grey darken-1"
                empty-icon="$ratingFull"
                half-increments
                hover
                small
              ></v-rating>
            </v-list-item-content>
            <v-list-item-action class="played" v-if="isPlay">
              <v-btn icon @click="stopPlay">
                <v-icon  color="grey lighten-1" large
                  >mdi-pause-circle-outline</v-icon>
              </v-btn>
            </v-list-item-action>
            <v-list-item-action class="played" v-else>
              <v-btn icon @click="play(song)">
                <v-icon  color="grey lighten-1" large
                  >mdi-arrow-right-drop-circle</v-icon>
              </v-btn>
            </v-list-item-action>
          </v-list-item>
          <v-divider color="grey" class="mx-6"></v-divider>
        </v-list>
      </v-col>
    </v-row>
  </v-card>
</template>
<script>
export default {
  emits: ["asong"],
  data: () => ({
    isPlay: false,
    player: new Audio(),
    songs: [
      {
        title: "Solo again",
        artist: "Vanda",
        listner: "90K",
        img: "vanda.jpg",
        rated: 3.5,
        src : require('../assets/vanda.mp3')
      },
      {
        title: "Solo 100years",
        artist: "Vantheav",
        listner: "90K",
        img: "vantheav.jpg",
        rated: 5,
        src : require('../assets/vantheav.mp3')
      },
      {
        title: "MUSIC FOR GAME PLAY",
        artist: "Vantheav",
        listner: "100M",
        img: "1.jpg",
        rated: 5,
        src : require('../assets/game.mp3')
      },
      {
        title: "ចាប់ផ្ដើមហើយនឹងបញ្ចប់",
        artist: "Vanda",
        listner: "90K",
        img: "2.jpg",
      },
      {
        title: "where are you now?",
        artist: "Vanda",
        listner: "90K",
        img: "3.jpg",
      },
      {
        title: "Gqeen Bee",
        artist: "Vanda",
        listner: "90K",
        img: "4.jpg",
      },
      {
        title: "IF I DIE",
        artist: "Vanda",
        listner: "90K",
        img: "5.jpg",
      },
      {
        title: "HIK HIK",
        artist: "Vanda",
        listner: "90K",
        img: "6.jpg",
      },
      {
        title: "BE WITH ME",
        artist: "Vanda",
        listner: "90K",
        img: "7.jpg",
      },
      {
        title: "រាំញីកែងជើង",
        artist: "G-devith",
        listner: "90K",
        img: "GDevith.jpg",
      },
      {
        title: "Solo ",
        artist: "Vanda",
        listner: "1M",
        img: "vanda.jpg",
      },
      {
        title: "ឈឺទេ",
        artist: "Vanda",
        listner: "100K",
        img: "vanda.jpg",
      },
      {
        title: "Time to rise",
        artist: "Vanda",
        listner: "30M",
        img: "vanda.jpg",
      },
    ],
  }),
  methods: {
    play(song) {
      this.$emit("asong", song);
      console.log(song);
        this.player.src = song.src;
        this.player.play()
        this.isPlay = true
    },
    stopPlay(){
        this.isPlay = false;
        this.player.pause();
    }
  },
};
</script >

<style scoped>
.rounded-lg {
  margin: 30px;
}
.played{
    margin-right: 20px;
}
</style>