<script>
export default {
  name: "Header",
  props: ["userName"],

  data() {
    return {
      hourStatus: "",
      currentDate: "",
    };
  },
  mounted() {
    const currentHour = new Date().getHours();
    if (currentHour < 12) {
      this.hourStatus = "Morning";
    } else if (currentHour < 17) {
      this.hourStatus = "Afternoon";
    } else {
      this.hourStatus = "Evening";
    }
    const today = new Date();
    const options = { day: "numeric", month: "long", year: "numeric" };
    this.currentDate = today.toLocaleDateString("en-US", options);
  },
};
</script>

<template>
  <header>
    <div class="flex justify-between p-5 space-x-48">
      <div class="flex space-x-3">
        <div>
          <img
            src="/assets/avatar-image.webp"
            alt="Avatar"
            class="h-14 rounded-full border-2"
          />
        </div>
        <div class="space-y-1">
          <div class="text-3xl font-bold">
            {{ hourStatus }}
            {{ userName }}
          </div>
          <div class="text-slate-500">
            <p>
              Here are your stats for Today:
              <span>
                {{ currentDate }}
              </span>
            </p>
          </div>
        </div>
      </div>
      <div class="flex space-x-5">
        <div>
          <button
            type="button"
            class="inline-block px-4 py-1 border-2 border-gray-200 text-gray-800 font-bold text-xs
            leading-tight rounded-full hover:shadow-sm"
          >
            Today
          </button>
        </div>
        <div>
          <span class="text-slate-500">compared to</span>
        </div>
        <div>
          <button
            class="flex bg-smoke-300 text-gray-700 shadow-md rounded-full px-2 py-1 text-sm h-8 w-22"
          >
            Previous
            <div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-5 h-6 text-cyan-500"
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
      </div>
    </div>
  </header>
</template>
