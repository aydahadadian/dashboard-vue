<template>
  <Bar
    id="bar-chart"
    :chart-options="options"
    :chart-data="chartData"
    :chart-id="chartId"
    :dataset-id-key="datasetIdKey"
    :plugins="plugins"
  />
</template>

<script>
import { Bar } from "vue-chartjs/legacy";
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
} from "chart.js";

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

export default {
  name: "BarChart",
  components: { Bar },

  data() {
    return {
      chartData: {
        labels: ["M", "T", "W", "T", "F", "S", "S"],
        datasets: [
          {
            // pointBorderColor: "#2554FF",
            label: "Data One",
            backgroundColor: "#ffff",
            data: [50, 20, 10, 22, 50, 10, 40],
            fill: false,
            borderColor: "transparent",
            borderWidth: 19,
            gridLines: false
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
              color: "#ffffff",
              dashOffset: 0.8
            }
          },
          xAxes: {
            grid: {
              color: "#dddddd81"
            },
            ticks: {
              color: "#ffffff",
              fontSize: 12,
              dashOffset: 0.8
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
#bar-chart {
  height: 180px;
  padding:5px 10px;
}
</style>
