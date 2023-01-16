<script>
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";
import RevenueAnalysis from "./components/RevenueAnalysis.vue";
import CategoryAnalysis from "./components/CategoryAnalysis.vue";
import ProgressiveLineChart from "./components/ProgressiveLineChart.vue";

export default {
  name: "App",
  components: {
    Header,
    Sidebar,
    RevenueAnalysis,
    CategoryAnalysis,
    ProgressiveLineChart,
  },
};
</script>

<template>
  <div class="flex">
    <!-- Sidebar -->
    <div class="w-[300px]">
      <Sidebar />
    </div>
    <!-- Main Frame-->
    <div class="w-full">
      <!-- Header -->
      <header class="!w-full">
        <Header userName="Aman" />
      </header>
      <!-- Revenue -->
      <div class="px-5"><RevenueAnalysis /></div>
      <div class="p-3">
        <ProgressiveLineChart />
      </div>
      <div>
        <CategoryAnalysis />
      </div>
    </div>
  </div>
</template>
