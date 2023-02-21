<template>
  <v-avatar
    class="rounded-lg ms-4 mt-n8 shadow"
    :color="color"
    elevation="24"
    height="64"
    rounded
    width="64"
  >
    <v-icon color="white" dense>
      {{ icon }}
    </v-icon>
  </v-avatar>
</template>

<script>
export default {
  props: ["icon", "color"]
};
</script>
