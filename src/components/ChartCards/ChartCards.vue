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
        :Color="item.color"
      />
    </v-col>
  </v-row>
</template>
<script>
import Card from "./Card.vue";
export default {
  components: { Card },
  data: () => ({
    items: [
      {
        color: "red",
        title: "Website Views",
        text: "Last Campaign Performance",
        time: "ecampaign sent 2 days ago"
      },
      {
        color: "red",
        title: "Daily Sales",
        text: "(+15%) increase in today sales.",
        time: "updated 4 min ago"
      },
      {
        color: "red",
        title: "Completed Tasks",
        text: "Last Campaign Performance",
        time: "just updated"
      }
    ]
  })
};
</script>
