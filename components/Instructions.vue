<template>
  <v-expansion-panels>
    <v-expansion-panel>
      <v-expansion-panel-header>
        {{ instructionHeader }}
      </v-expansion-panel-header>
      <v-expansion-panel-content class="text-left">
        <pre>{{ instructionText }}</pre>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
</template>

<script>
export default {
  computed: {
    instructionHeader() {
      return "Instructions";
    },
    instructionText() {
      var string = `1. Select the symbols that are needed for the extra red box by clicking the active button on the card with the relevant symbol
2. This will move the symbol from the 'All Symbols' section to the 'Active Symbols' section
3. When you enable a symbol, press the toggle complete button
4. This will mark the symbol is complete
5. Once all three symbols have been activated, some text will appear in the lower left of the screen and you will be rewarded with a guaranteed red border weapon

Note: This is available on an account basis, you will only get the extra red border weapon once a week!
`;
      return string;
    },
  },
};
</script>

<style scoped>
pre {
  overflow-wrap: normal;
  overflow: scroll;
}
</style>
