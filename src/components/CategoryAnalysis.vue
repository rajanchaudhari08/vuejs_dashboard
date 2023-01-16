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
  <div class="px-2">
    <div class="flex">
      <div>
        <div class="flex justify-between px-2 shadow-sm rounded-full">
          <button
            class="active:text-slate-800 active:font-bold underline decoration-solid decoration-cyan-500 
            decoration-2 underline-offset-8 font-semibold text-md h-7"
          >
            Automations
          </button>
          <button
            class="text-slate-400 font-semibold text-md hover:font-bold
            rounded-full hover:bg-cyan-50 hover:text-slate-800 h-7
            px-2"
          >
            Campaigns
          </button>
          <button
            class="text-slate-400 font-semibold text-md hover:font-bold
            rounded-full hover:bg-cyan-50 hover:text-slate-800
            px-2"
          >
            Segments
          </button>
          <button
            class="flex bg-smoke-300 text-slate-900 font-semibold border-2 border-slate-200
            rounded-full px-3 py-1 text-sm h-8"
          >
            <p>Last Month</p>
            <div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-5 h-5 text-cyan-500"
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
