<template>
  <LineChartGenerator
    id="line-chart"
    :chart-options="options"
    :chart-data="chartData"
    :chart-id="chartId"
    :dataset-id-key="datasetIdKey"
    :plugins="plugins"
  />
</template>

<script>
import { Line as LineChartGenerator } from "vue-chartjs/legacy";

import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  LineElement,
  LinearScale,
  CategoryScale,
  PointElement
} from "chart.js";

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  LineElement,
  LinearScale,
  CategoryScale,
  PointElement
);

export default {
  name: "LineChart",
  components: {
    LineChartGenerator
  },
  props:['data'],

  data() {
    return {
      chartData: {
        labels: ["Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"],
        datasets: [
          {
            label: "Data One",
            backgroundColor: "#ffff",
            data: [50, 40, 300, 315, 330, 350, 200, 230, 500],
            fill: false,
            borderColor: "#fff",
            borderWidth: 3
          }
        ]
      },
      options: {
        scales: {
          yAxes: {
            grid: {
              color: "#dddddd81"
            },
            ticks: {
              color: "#ffffff"
            }
          },
          xAxes: {
            grid: {
              display: false,
              color: "#dddddd81"
            },
            ticks: {
              color: "#ffffff",
              fontSize: 12
            }
          }
        },
        plugins: {
          legend: {
            display: false
          }
        },

        responsive: true,
        maintainAspectRatio: false
      }
    };
  }
};
</script>
<style>
#line-chart {
  height: 180px;
  padding: 5px 10px;
}
</style>
