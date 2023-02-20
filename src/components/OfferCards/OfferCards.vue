<template>
  <v-row class="mb-6 mt-10">
    <v-col
      v-for="item in items"
      :key="item.title"
      class="pt-0 mb-lg-0 mb-10 col-lg-4"
    >
      <Card
        :title="item.title"
        :description="item.description"
        :img="item.img"
        :location="item.location"
        :price="item.price"
      />
    </v-col>
  </v-row>
</template>

<script>
import Card from "./Card.vue";
import offer1 from "../../assets/offer/offer-1.jpeg";
import offer2 from "../../assets/offer/offer-2.jpeg";
import offer3 from "../../assets/offer/offer-3.jpeg";

export default {
  data: () => ({
    components: { Card },
    items: [
      {
        img: offer1,
        title: "Cozy 5 Stars Apartment",
        description:
          "The place is close to Barceloneta Beach and bus stop just 2 min by walk and near to 'Naviglio' where you can enjoy the main night life in Barcelona.",
        price: "899",
        location: "Barcelona, Spain",
      },
      {
        img: offer2,
        title: "Office Studio",
        description:
          "The place is close to Barceloneta Beach and bus stop just 2 min by walk and near to 'Naviglio' where you can enjoy the main night life in Barcelona.",
        price: "1.119",
        location: "London, UK",
      },
      {
        img: offer3,
        title: "Beautiful Castle",
        description:
          "The place is close to Barceloneta Beach and bus stop just 2 min by walk and near to 'Naviglio' where you can enjoy the main night life in Barcelona.",
        price: "459",
        location: "Milan, Italy",
      },
    ],
  }),
  components: { Card },
};
</script>
