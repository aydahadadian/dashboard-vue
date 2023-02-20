<template>
  <v-card
    class="card-shadow border-radius-xl py-5 text-center v-card v-sheet theme--light"
  >
    <div class="mt-n11 mx-4 position-relative z-index-2 card-header">
      <div
        class="mt-n14 mx-1 card-header position-relative z-index-2 image-container"
      >
        <v-img
          :src="img"
          class="img-fluid shadow border-radius-lg rounded-lg"
        />
        <div
          class="colored-shadow"
          style="background-image: url(''img'');"
        ></div>
      </div>
    </div>
    <div class="d-flex justify-center mx-auto mt-n7">
      <v-icon
        class="notranslate rounded px-5 theme--light"
        style="font-size: 18px;"
        color="var(--v-error-base)"
        >mdi-refresh</v-icon
      >

      <v-icon
        class="notranslate rounded  px-5  theme--light"
        style="font-size: 18px;"
        color="var(--v-primary-base)"
        >mdi-pencil</v-icon
      >
    </div>
    <p class="text-h6 font-weight-normal text-typo text-h5 mt-7 mb-2 px-4">
      {{ title }}
    </p>
    <p class="mb-0 text-body font-weight-light px-5">
      {{ description }}
    </p>
    <v-divider class="horizontal dark my-6"></v-divider>
    <div class="d-flex text-body mx-2 px-4 justify-space-between">
      <p class="mb-0 font-weight-normal text-body">${{ price }}/night</p>
      <div class="d-flex text-subtitle-2">
        <v-icon
          class="me-1
                my-auto
              "
          >mdi-map-marker</v-icon
        >
        <p class="text-sm my-auto font-weight-light">{{ location }}</p>
      </div>
    </div>
  </v-card>
</template>
<script>
export default {
  props: ["title", "description", "location", "price", "img"],
};
</script>

<style>
.colored-shadow {
  transform: scale(0.94);
  top: 0.5%;
  filter: blur(12px);
  position: absolute;
  left: 0px;
  width: 100%;
  height: 100%;
  background-size: cover;
  z-index: -1;
}
.card-header {
  z-index: 1;
  position: relative;
}
.card-header:hover .image-container {
  transform: translateY(-30px);
}
</style>
