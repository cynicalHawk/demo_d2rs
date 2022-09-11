<template>
  <v-row>
    <v-col class="text-center">
      <h1 class="text-center">Kings Fall</h1>
      <RedBoxCards :symbols="KF_DEFAULT_SYMBOLS"/>
    </v-col>
  </v-row>
</template>

<script>
import RedBoxCards from "../components/RedBoxCards.vue";
import RedBoxCard from "../components/RedBoxCard.vue";
export default {
  components: { RedBoxCards, RedBoxCard },
  computed: {
    KF_DEFAULT_SYMBOLS() {
      return [
        {
          id: 1,
          location: "Opening Encounter",
          img: "kf_symbols/kf_symbol1.jpg",
          description:
            "After completing the opening encounter and going through the portal, jump on the first swinging lamp and turn around. The circle is directly below the platform below you",
        },
        {
          id: 2,
          location: "Opening Encounter",
          img: "kf_symbols/kf_symbol2.jpg",
          description:
            "This circle can be found on the wall directly behind the first secret chest. After riding the tombship across the chasm (second part of the jumping puzzle), jump off early and head left up the wall, then head through a hole in the wall to find the chest and circle",
        },
        {
          id: 3,
          location: "Totems Encounter",
          img: "kf_symbols/kf_symbol3.jpg",
          description:
            "After completing the totems encounter, head into the left side room. The circle is on the wall behind the balcony where the knights spawn, towards the right side",
        },
        {
          id: 4,
          location: "Warpriest encounter",
          img: "kf_symbols/kf_symbol4.jpg",
          description:
            "after defeating the warpriest, this circle can be found on the wall by the right side balcony",
        },
        {
          id: 5,
          location: "Warpriest encounter",
          img: "kf_symbols/kf_symbol5.jpg",
          description:
            "After making your way through Golgoroth's Maze, the next circle is on the inside walls of the final hole, directly before the door to Golgoroth",
        },
        {
          id: 6,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol6.jpg",
          description:
            "After defeating Golgoroth, head into the room on the lower floor, directly behind where the first orb drops. The circle is on the wall.",
        },
        {
          id: 7,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol7.jpg",
          description:
            "Make your way through the second jumping puzzle and pull out your ghost to reveal hidden platforms. Across these is a room where you will find the second secret chest. The circle is directly beside it",
        },
        {
          id: 8,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol8.jpg",
          description:
            "After completing the jumping puzzle, the next circle can be found on the ceiling directly in front of the door to the door at the end",
        },
        {
          id: 9,
          location: "Golgoroth encounter",
          img: "kf_symbols/kf_symbol9.jpg",
          description:
            "After entering the final arena, turn around and look up. The symbol is on the wall above the door you entered through",
        },
      ];
    },
  },
};
</script>
