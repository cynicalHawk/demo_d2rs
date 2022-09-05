<template>
  <v-row>
    <v-col class="text-center">
      <h1 class="text-center">Kings Fall</h1>
      <RedBoxCards/>
    </v-col>
  </v-row>
</template>

<script>
import RedBoxCards from '../components/RedBoxCards.vue';
import RedBoxCard from '../components/RedBoxCard.vue';
export default {
    components: { RedBoxCards, RedBoxCard }
}
</script>
