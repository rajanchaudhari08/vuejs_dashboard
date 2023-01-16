<template>
  <LineGenerate :data="data" :options="options" />
</template>

<script>
import { Line as LineGenerate } from "vue-chartjs";

import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
} from "chart.js";

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
);

ChartJS.defaults.font.family = "Sans-Serif";
ChartJS.defaults.font.style = "italic";
ChartJS.defaults.font.weight = "300";

// this  is generate data1 and data2
const data1 = [];
const data2 = [];
let prev = 100;
let prev2 = 80;

//
for (let i = 0; i < 100; i++) {
  prev += 5 - Math.random() * 10;
  data1.push({ x: i, y: prev });
  prev2 += 5 - Math.random() * 10;
  data2.push({ x: i, y: prev2 });
}

const data = {
  datasets: [
    {
      borderColor: "#cffafe",
      borderWidth: 1,
      radius: 0,
      data: data1,
    },
    {
      borderColor: "#06b6d4",
      borderWidth: 1,
      radius: 0,
      data: data2,
    },
  ],
};

const options = {
  responsive: true,
  maintainAspectRatio: false,
  interaction: {
    intersect: false,
  }, // where?
  plugins: {
    legend: false,
  },
  scales: {
    x: {
      type: "linear",
      grid: {
        display: false,
      },
    },
    y: {
      grid: {
        display: false,
      },
    },
  },
};

export default {
  name: "ProgressiveLineChart",
  components: {
    LineGenerate,
  },
  data() {
    return {
      data: data,
      options: options,
    };
  },
};
</script>
