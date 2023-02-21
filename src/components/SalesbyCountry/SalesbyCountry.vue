<template>
  <v-card
    class=" card-shadow rounded-lg d-flex flex-column theme--light"
    shaped
    rounded
    tile
  >
    <div class="pt-4 pb-0 d-flex">
      <IconCard icon="mdi-web" color="green" />
      <p class="pa-0  font-weight-bold text-h6 ms-3 text-typo text-subtitle-1">
        Sales by country
      </p>
    </div>
    <v-container>
      <v-row v-for="n in 1" :key="n" class="mb-6">
        <v-col class="col-md-7 col-lg-6 col">
          <CountryList />
        </v-col>
        <v-col class="col-md-5 col-lg-6 col">
          <JvectorMap />
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
import IconCard from "../Commons/IconCard.vue";
import CountryList from "./CountryList.vue";
import JvectorMap from "./JvectorMap.vue";

export default {
  components: {
    IconCard,
    CountryList,
    JvectorMap
  }
};
</script>
