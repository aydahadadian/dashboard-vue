<template>
  <v-row class="ma-0 mb-6" no-gutters style="gap: 15px;">
    <v-col v-for="item in items" :key="item.title" class="pa-0 mt-8">
      <Card
        :title="item.title"
        :value="item.value"
        :report-value="item.reportValue"
        :report="item.report"
        :icon="item.icon"
        :color="item.color"
      />
    </v-col>
  </v-row>
</template>

<script>
import Card from "./Card.vue";

export default {
  data: () => ({
    items: [
      {
        icon: "mdi-sofa-single",
        color: "black",
        title: "Bookings",
        value: "281",
        reportValue: "+55%",
        report: "than last week"
      },
      {
        icon: "mdi-poll",
        color: "red",
        title: "Todays Users",
        value: "2,300",
        reportValue: "+3%",
        report: "than last month"
      },
      {
        icon: "mdi-account-plus-outline",
        color: "green",
        title: "Revenue",
        value: "34k",
        reportValue: "+1%",
        report: "than yesterday"
      },
      {
        icon: "mdi-store",
        color: "blue",
        title: "Followers",
        value: "+91",
        report: "Just updated"
      }
    ]
  }),
  components: { Card }
};
</script>
