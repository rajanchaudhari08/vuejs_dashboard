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
    <div class="w-[225px] max-h-screen">
      <Sidebar />
    </div>
    <!-- Main Frame-->
    <div class="w-full max-h-screen">
      <!-- Header -->
      <header>
        <Header userName="Adam" />
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
