<template>
  <v-row>
    <v-col class="text-center">
      <h1 class="text-center">Kings Fall</h1>
      <Instructions />
      <RedBoxCards :symbols="KF_DEFAULT_SYMBOLS" localStoragePrefix="KF" />
    </v-col>
  </v-row>
</template>

<script>
import RedBoxCards from "../components/RedBoxCards.vue";
import Instructions from "../components/Instructions.vue";
export default {
  components: { RedBoxCards, Instructions },
  computed: {
    KF_DEFAULT_SYMBOLS() {
      return [
        {
          id: 1,
          location: "Opening Encounter",
          img: "kf_symbols/kf_symbol1.png",
          description:
            "After completing the opening encounter and going through the portal, jump on the first swinging lamp and turn around. The circle is directly below the platform below you",
          isComplete: false,
        },
        {
          id: 2,
          location: "Opening Encounter",
          img: "kf_symbols/kf_symbol2.png",
          description:
            "This circle can be found on the wall directly behind the first secret chest. After riding the tombship across the chasm (second part of the jumping puzzle), jump off early and head left up the wall, then head through a hole in the wall to find the chest and circle",
          isComplete: false,
        },
        {
          id: 3,
          location: "Totems Encounter",
          img: "kf_symbols/kf_symbol3.png",
          description:
            "After completing the totems encounter, head into the left side room. The circle is on the wall behind the balcony where the knights spawn, towards the right side",
          isComplete: false,
        },
        {
          id: 4,
          location: "Warpriest encounter",
          img: "kf_symbols/kf_symbol4.png",
          description:
            "after defeating the warpriest, this circle can be found on the wall by the right side balcony",
          isComplete: false,
        },
        {
          id: 5,
          location: "Warpriest encounter",
          img: "kf_symbols/kf_symbol5.png",
          description:
            "After making your way through Golgoroth's Maze, the next circle is on the inside walls of the final hole, directly before the door to Golgoroth",
          isComplete: false,
        },
        {
          id: 6,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol6.png",
          description:
            "After defeating Golgoroth, head into the room on the lower floor, directly behind where the first orb drops. The circle is on the wall.",
          isComplete: false,
        },
        {
          id: 7,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol7.png",
          description:
            "Make your way through the second jumping puzzle and pull out your ghost to reveal hidden platforms. Across these is a room where you will find the second secret chest. The circle is directly beside it",
          isComplete: false,
        },
        {
          id: 8,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol8.png",
          description:
            "After completing the jumping puzzle, the next circle can be found on the ceiling directly in front of the door to the door at the end",
          isComplete: false,
        },
        {
          id: 9,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol9.png",
          description:
            "After entering the final arena, turn around and look up. The symbol is on the wall above the door you entered through",
          isComplete: false,
        },
      ];
    },
  },
};
</script>
