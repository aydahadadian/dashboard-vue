<template>
  <v-card class="card-shadow rounded-lg px-4 py-5 v-sheet theme--light">
    <v-sheet
      class="shadow-primary  rounded-lg py-3 pe-1 mb-6 mt-n12"
      :class="bc"
    >
      <component :is="chart" />
  </v-sheet>
    <h6 class="ms-2 mt-6 mb-0 text-h6 font-weight-bold text-typo">
      {{ title }}
    </h6>
    <p class="text-sm ms-2 text-body font-weight-light">
      {{ text }}
    </p>
    <v-divider class="mb-4 mx-2"></v-divider>
    <div class="d-flex text-body mx-2">
      <v-icon class="text-sm my-auto me-1">mdi-schedule</v-icon>
      <p class="mb-0 text-sm font-weight-light text-body">
        {{ time }}
      </p>
    </div>
  </v-card>
</template>

<script>
import BarChart from "./Charts/Bar.vue";
import LineChart from "./Charts/Line.vue";

export default {
  name: "Card",
  // eslint-disable-next-line vue/no-unused-components
  components: { BarChart, LineChart },

  props: ["title", "text", "time", "bc", "chart"]
};
</script>
