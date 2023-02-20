<template>
  <div class="dashboard">
    <SalesbyCountry />
    <ReportCards />
  </div>
</template>

<script>
import ReportCards from "../components/ReportCards/ReportCards.vue";
import SalesbyCountry from "../components/SalesbyCountry/SalesbyCountry.vue";

export default {
  components: { SalesbyCountry, ReportCards },
};
</script>
