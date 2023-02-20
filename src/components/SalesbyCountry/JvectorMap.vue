<template>
  <div
    id="map"
    class="mt-0 mt-lg-n4 w-100 h-100 overflow-hidden jvm-container"
    style="height: 100%;"
  ></div>
</template>

<script>
window.jQuery = require("jquery");
require("jvectormap");
require("../../assets/jquery-jvectormap-2.0.5.css");
require("../../assets/jquery-jvectormap-2.0.5.min.js");
require("../../assets/jquery-jvectormap-world-merc.js");

var $ = window.jQuery;

export default {
  name: "WorldMap",
  mounted() {
    this.initMap();
  },

  methods: {
    initMap() {
      $("#map").vectorMap({
        map: "world_merc",
        backgroundColor: "transparent",
        hoverOpacity: 0.7,
        hoverColor: false,
        zoomOnScroll: false,
        zoomButtons: false,
        markersSelectable: true,

        regionStyle: {
          initial: {
            fill: "#dde2e8",
          },
        },
        markerStyle: {
          initial: {
            fill: "#ff0057",
            stroke: "#ff0057",

            "stroke-opacity": 0.7,
            r: 5,
          },
          selected: {
            fill: "#000000",
          },
        },
        markerLabelStyle: {
          initial: {
            fill: "#007bff",
          },
        },

        scaleColors: ["#C8EEFF", "#0071A4"],
        markers: [
          { latLng: [-14.235, -51.9253], name: "Brazil" },
          { latLng: [51.1657, 10.4515], name: "Germany" },
          { latLng: [36.1304, -80.3468], name: "USA" },
          { latLng: [35.8617, 104.1954], name: "China" },
          { latLng: [61.524, 105.3188], name: "Russia" },
        ],
      });
    },
  },
};
</script>
