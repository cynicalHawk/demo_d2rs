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
        :isComplete="k.isComplete"
        :active="true"
        @deactivate="deactivate"
        @toggleComplete="toggleComplete"
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
  props: ['symbols', 'localStoragePrefix'],
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
      localStorage.setItem(this.LSHasStoredData, true);
      localStorage.setItem(this.LSActiveSymbols, JSON.stringify(this.activeSymbols));
      localStorage.setItem(this.LSAllSymbols, JSON.stringify(this.allSymbols));
    },
    retrieveFromLocalStorage() {
      if (localStorage.getItem(this.LSHasStoredData)) {
        this.activeSymbols = JSON.parse(localStorage.getItem(this.LSActiveSymbols));
        this.allSymbols = JSON.parse(localStorage.getItem(this.LSAllSymbols));
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
    getActiveIndexById(id) {
      var item = this.activeSymbols.find((element) => element.id == id);
      return this.activeSymbols.indexOf(item);
    },
    toggleComplete(id) {
      var currIsComplete = this.activeSymbols[this.getActiveIndexById(id)].isComplete;
      this.activeSymbols[this.getActiveIndexById(id)].isComplete = !currIsComplete;
      this.saveToLocalStorage();
    },
  },
  mounted() {
    this.retrieveFromLocalStorage();
  },
  computed: {
    LSHasStoredData() {
      return this.localStoragePrefix + "|hasStoredData";
    },
    LSActiveSymbols() {
      return this.localStoragePrefix + "|activeSymbols";
    },
    LSAllSymbols() {
      return this.localStoragePrefix + "|allSymbols";
    },
  },
};
</script>
