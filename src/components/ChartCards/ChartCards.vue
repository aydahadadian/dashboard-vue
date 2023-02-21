<template>
  <v-row class=" mb-6 mt-15">
    <v-col
      class="pt-0 mb-lg-0 mb-10 col-lg-4"
      v-for="item in items"
      :key="item.title"
    >
      <Card
        :title="item.title"
        :text="item.text"
        :time="item.time"
        :bc="item.bc"
        :chart="item.chart"
      />
    </v-col>
  </v-row>
</template>
<script>
import Card from "./Card.vue";
import LineChart from "./Charts/Line.vue";
import BarChart from "./Charts/Bar.vue";
export default {
  components: { Card },
  data: () => ({
    items: [
      {
        chart: BarChart,
        bc: "pink",
        title: "Website Views",
        text: "Last Campaign Performance",
        time: "ecampaign sent 2 days ago"
      },
      {
        chart: LineChart,
        bc: "green",
        title: "Daily Sales",
        text: "(+15%) increase in today sales.",
        time: "updated 4 min ago"
      },
      {
        chart: LineChart,
        bc: "black",
        title: "Completed Tasks",
        text: "Last Campaign Performance",
        time: "just updated"
      }
    ]
  })
};
</script>
