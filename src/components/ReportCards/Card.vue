<template>
  <v-card
    class="mb-6 card-shadow py-4 v-sheet theme--light rounded-lg"
    shaped
    rounded
    tile
  >
    <v-row class="px-4">
      <v-col class="col-4"> <IconCard :icon="icon" :color="color"/></v-col>
      <v-col class="col-8 text-end ">
        <p
          class="mb-0 text-capitalize text-body text-body-2 font-weight-light "
        >
          {{ title }}
        </p>
        <h6 class="text-h6 text-typo font-weight-bolder mb-0">
          {{ value }}
        </h6>
      </v-col>
      <v-divider
        class="dark mt-3 mb-4"
        style="width: 100%;flex:none"
      ></v-divider>
      <v-row class="mb-0 text-body px-4">
        <v-col class="col-12">
          <p class="mb-0 text-body">
            <span
              class="success--text text-sm font-weight-bolder"
              :v-if="reportValue"
              >{{ reportValue }}</span
            >
            <span class="font-weight-light ms-1">{{ report }}</span>
          </p>
        </v-col>
      </v-row>
    </v-row>
  </v-card>
</template>

<script>
import { title } from "process";
import IconCard from "../Commons/IconCard.vue";

export default {
  props: ["icon", "color", "title", "value", "report", "reportValue"],
  components: { IconCard },
};
</script>
