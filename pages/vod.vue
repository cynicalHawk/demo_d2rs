<template>
  <v-row>
    <v-col class="text-center">
      <h1 class="text-center">Vow of the Disciple</h1>
      <RedBoxCards :symbols="VOD_DEFAULT_SYMBOLS" localStoragePrefix="VOD" />
    </v-col>
  </v-row>
</template>

<script>
import RedBoxCards from "../components/RedBoxCards.vue";
export default {
  name: "vow-of-the-disciple",
  components: { RedBoxCards },
  computed: {
    VOD_DEFAULT_SYMBOLS() {
      return [
        {
          id: 1,
          location: "Opening Encounter",
          img: "vod_symbols/vod_symbol1.png",
          description:
            "After you drop down, turn around. Opposite the direction for the first encounter",
          isComplete: false,
        },
        {
          id: 2,
          location: "Opening Encounter",
          img: "vod_symbols/vod_symbol2.png",
          description:
            "After the major symbol room, before the first encounter. Shard to shoot is in that middle room",
          isComplete: false,
        },
        {
          id: 3,
          location: "Opening Encounter",
          img: "vod_symbols/vod_symbol3.png",
          description:
            "In the area of the first encounter but do not start encounter. A shard will be on the left on top of a structure to open a room on the left side",
          isComplete: false,
        },
        {
          id: 4,
          location: "Acquisition(First) encounter",
          img: "vod_symbols/vod_symbol4.png",
          description:
            "In room right before Caretaker encounter, jump up on ledge to shoot shard, door opens below",
          isComplete: false,
        },
        {
          id: 5,
          location: "Caretaker(Second) encounter",
          img: "vod_symbols/vod_symbol5.png",
          description:
            "After the Caretaker boss, same room where he dies, to the left, shoot shard, go to door",
          isComplete: false,
        },
        {
          id: 6,
          location: "Caretaker(Second) encounter",
          img: "vod_symbols/vod_symbol6.png",
          description:
            "Start of jumping puzzle in the outside room with the first darkness shard to move platforms with tons of scorn and before symbol wall. Boor and shard to open on the left",
          isComplete: false,
        },
        {
          id: 7,
          location: "Caretaker(Second) encounter",
          img: "vod_symbols/vod_symbol7.png",
          description:
            "In the area of the moving white pillars. Darkness shard is back right and opens a door next to it",
          isComplete: false,
        },
        {
          id: 8,
          location: "Upended(Third) encounter",
          img: "vod_symbols/vod_symbol8.png",
          description:
            "Upstairs on the left there is a shard hidden behind a wall. The door is hidden behind some pillars behind you",
          isComplete: false,
        },
        {
          id: 9,
          location: "Upended(Third) encounter",
          img: "vod_symbols/vod_symbol9.png",
          description:
            "Last jumping section before the boss fight. Jump up some floors and a shard is hidden in the sky, when shot, a door opens on the top right",
          isComplete: false,
        },
      ];
    },
  },
};
</script>
