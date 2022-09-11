<template>
  <v-container>
    <v-btn class="mt-2 mb-6" color="red" @click="reset"> Reset </v-btn>
    <h2>Active Symbols</h2>
    <v-layout row wrap justify-space-between class="my-4 py-4">
      <RedBoxCard
        class="pa-6 ma-2"
        v-for="k in activeSymbols"
        :key="k.id"
        :id="k.id"
        :location="k.location"
        :img="k.img"
        :description="k.description"
        :active="true"
        @deactivate="deactivate"
      />
    </v-layout>
    <h2 class="my-4 py-4">All Symbols</h2>
    <v-layout row wrap justify-space-between class="yx-4 py-4">
      <RedBoxCard
        class="pa-6 ma-2"
        v-for="k in allSymbols"
        :key="k.id"
        :id="k.id"
        :location="k.location"
        :img="k.img"
        :description="k.description"
        :active="false"
        @activate="activate"
      />
    </v-layout>
  </v-container>
</template>

<script>
import RedBoxCard from "./RedBoxCard.vue";

export default {
  props: ['symbols'],
  data() {
    return {
      activeSymbols: [],
      allSymbols: [],
    };
  },
  components: { RedBoxCard },
  methods: {
    sortArrays() {
      this.activeSymbols.sort((a, b) => a.id - b.id);
      this.allSymbols.sort((a, b) => a.id - b.id);
    },
    activate(id) {
      console.log("moving " + id + " from all to active");
      this.moveToActive(id);
    },
    moveToActive(id) {
      var item = this.allSymbols.find((element) => element.id == id);
      this.allSymbols.splice(this.allSymbols.indexOf(item), 1);
      this.activeSymbols.push(item);
      this.sortArrays();
      this.saveToLocalStorage();
    },
    deactivate(id) {
      console.log("moving " + id + " from active to all");
      this.moveToAll(id);
    },
    moveToAll(id) {
      var item = this.activeSymbols.find((element) => element.id == id);
      this.activeSymbols.splice(this.activeSymbols.indexOf(item), 1);
      this.allSymbols.push(item);
      this.sortArrays();
      this.saveToLocalStorage();
    },
    saveToLocalStorage() {
      localStorage.setItem("hasStoredData", true);
      localStorage.setItem("activeSymbols", JSON.stringify(this.activeSymbols));
      localStorage.setItem("allSymbols", JSON.stringify(this.allSymbols));
    },
    retrieveFromLocalStorage() {
      if (localStorage.getItem("hasStoredData")) {
        this.activeSymbols = JSON.parse(localStorage.getItem("activeSymbols"));
        this.allSymbols = JSON.parse(localStorage.getItem("allSymbols"));
      } else {
        this.allSymbols = this.symbols;
      }
    },
    reset() {
      this.activeSymbols = [];
      this.allSymbols = [];
      this.allSymbols = this.symbols;
      this.saveToLocalStorage();
    },
  },
  mounted() {
    this.retrieveFromLocalStorage();
  },
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
