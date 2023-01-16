<script>
import QuickNotification from "./QuickNotification.vue";
import GaugeChart from "./GaugeChart.vue";

export default {
  name: "CategoryAnalysis",
  components: {
    QuickNotification,
    GaugeChart,
  },
};
</script>

<template>
  <div class="m-2 px-2">
    <div class="flex">
      <div>
        <div class="flex justify-between px-2 shadow-sm rounded-full">
          <button
            class="active:text-gray-800 active:font-bold underline decoration-solid decoration-cyan-500 decoration-2 underline-offset-8 font-semibold text-md h-7"
          >
            Automations
          </button>
          <button
            class="text-violet-300 font-semibold text-md hover:font-bold hover:text-gray-800 h-7"
          >
            Campaigns
          </button>
          <button
            class="text-violet-300 font-semibold text-md hover:font-bold hover:text-gray-800 h-7"
          >
            Segments
          </button>
          <button
            class="flex bg-smoke-300 text-gray-700 shadow-md rounded-full px-2 py-1 text-sm h-8"
          >
            <p>Last Month</p>
            <div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-6 h-6 text-cyan-500"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M19.5 8.25l-7.5 7.5-7.5-7.5"
                />
              </svg>
            </div>
          </button>
        </div>


        <div class="w-[48rem]"><QuickNotification /></div>
      </div>

      <!-- Gauge Chart -->
      <div class="w-full"><GaugeChart /></div>
    </div>
  </div>
</template>
