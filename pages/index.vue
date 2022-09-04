<template>
  <v-row justify="center" align="center">
    <v-col>
      <router-link to="/kf">
        <v-img src="kf_oryx.jpg" max-height="300px" class="my-2">
          <v-container bg fill-height text-center>
            <v-layout align-center>
              <v-flex class="text-h1"> Kings Fall </v-flex>
            </v-layout>
          </v-container>
        </v-img>
      </router-link>
      <router-link to="/vod">
        <v-img src="vod_box.jpg" max-height="300px" class="my-2">
          <v-container bg fill-height text-center>
            <v-layout align-center>
              <v-flex class="text-h1"> Vow of the Disciple </v-flex>
            </v-layout>
          </v-container>
        </v-img>
      </router-link>
      <router-link to="/vog">
        <v-img src="vog_door.jpg" max-height="300px" class="my-2">
          <v-container bg fill-height text-center>
            <v-layout align-center>
              <v-flex class="text-h1"> Vault of Glass </v-flex>
            </v-layout>
          </v-container>
        </v-img>
      </router-link>
      <router-link to="/dsc">
        <v-img src="dsc_snow.jpg" max-height="300px" class="my-2">
          <v-container bg fill-height text-center>
            <v-layout align-center>
              <v-flex class="text-h1"> Deep Stone Crypt </v-flex>
            </v-layout>
          </v-container>
        </v-img>
      </router-link>
      <router-link to="/gos">
        <v-img src="gos_waterfall.jpg" max-height="300px" class="my-2">
          <v-container bg fill-height text-center>
            <v-layout align-center>
              <v-flex class="text-h1"> Garden of Salvation </v-flex>
            </v-layout>
          </v-container>
        </v-img>
      </router-link>
      <router-link to="/lw">
        <v-img src="lw_riven.jpg" max-height="300px" class="my-2">
          <v-container bg fill-height text-center>
            <v-layout align-center>
              <v-flex class="text-h1"> Last Wish </v-flex>
            </v-layout>
          </v-container>
        </v-img>
      </router-link>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>

<style scoped>
a {
  text-decoration: none;
}
</style>
