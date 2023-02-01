<script>
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";
import RevenueAnalysis from "./components/RevenueAnalysis.vue";
import CategoryAnalysis from "./components/CategoryAnalysis.vue";
import ProgressiveLineChart from "./components/ProgressiveLineChart.vue";

export default {
  name: "App",
  data() {
    return {
      isOpen: false,
    }
  },
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
  <div class="flex w-full">
    <!-- Sidebar -->
    <div class=" max-h-screen">
      <Sidebar :isOpen="isOpen" @onClick="isOpen = !isOpen" />
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
        <!-- we need render this  wait -->
        <ProgressiveLineChart :key="isOpen ? 0 : 1" />
      </div>
      <div>
        <CategoryAnalysis />
      </div>
    </div>
  </div>
</template>
