<template>
  <div class="dashboard">
    <SalesbyCountry />
    <ChartCards />
    <ReportCards />
    <OfferCards />
  </div>
</template>

<script>
import ReportCards from "../components/ReportCards/ReportCards.vue";
import SalesbyCountry from "../components/SalesbyCountry/SalesbyCountry.vue";

import OfferCards from "../components/OfferCards/OfferCards.vue";
import ChartCards from "../components/ChartCards/ChartCards.vue";

export default {
  components: { SalesbyCountry, ReportCards, OfferCards, ChartCards }
};
</script>
