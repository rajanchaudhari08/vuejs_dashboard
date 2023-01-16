<template>
  <!-- Main -->
  <div class="grid justify-center">
    <!-- Text + Arrow -->
    <div class="flex justify-center space-y-1">
      <!-- Text -->
      <div class="text-2xl text-cyan-500 font-bold">Level 5</div>
      <!-- Arrow -->
      <div class="p-1">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          class="w-5 h-5 text-cyan-500"
        >
          <path
            fill="currentColor"
            d="M16.72 7.72a.75.75 0 011.06 0l3.75 3.75a.75.75 0 010 1.06l-3.75 3.75a.75.75 0 11-1.06-1.06l2.47-2.47H3a.75.75 0 010-1.5h16.19l-2.47-2.47a.75.75 0 010-1.06z"
          />
        </svg>
      </div>
    </div>
    <!-- Paragraph -->
    <div class="text-sm text-slate-500">+$32,050 in the last month</div>
  </div>
  <div>
    <Doughnut :data="data" :options="{
    
      elements: {
        
        arc: {
          borderRadius: 0,
          borderWidth: 12,

        }
      }
    }" />
  </div>
</template>

<script>
import { Doughnut } from "vue-chartjs";

import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  ArcElement,
} from "chart.js";

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  ArcElement
);

const data = {
  labels: ["Blue", "White"],
  datasets: [
    {
      data: [75, 25],
      backgroundColor: ["blue", "white"],
      hoverOffset: 4,
    },
  ],
};

const options = {
  maintainAspectRatio: false,
  responsive: true,
  elements: {
    arc: {
      borderWidth: 12,
    },
  },
  rotation: 270,
  circumference: 180,
};

export default {
  name: "GaugeChart",
  components: {
    Doughnut,
  },
  data() {
    return {
      data: data,
      options: options,
    };
  },
};
</script>
