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
    const options = { day: "numeric", month: "short", year: "numeric" };
    this.currentDate = today.toLocaleDateString("en-US", options);
  },
};
</script>

<template>
  <header>
    <div class="flex justify-between p-4">
      <div class="flex space-x-3">
        <div>
          <img
            src="/assets/avatar-image.webp"
            alt="Avatar"
            class="h-14 rounded-full border-2"
          />
        </div>
        <div>
          <div class="text-2xl font-semibold">
            Good {{ hourStatus }}
            {{ userName }}
          </div>
          <div class="text-[14px] text-slate-500">
            <p>
              Here are your stats for Today:
              <span>
                {{ currentDate }}
              </span>
            </p>
          </div>
        </div>
      </div>
      <div class="flex space-x-2">
        <div>
          <button
            type="button"
            class="inline-block px-3 py-1 border-2 border-slate-200 text-slate-800 font-bold text-sm leading-tight rounded-full hover:shadow-sm"
          >
            Today
          </button>
        </div>
        <div>
          <span class="text-slate-500 text-sm">compared to</span>
        </div>
        <div>
          <button
            class="flex text-slate-800 border-2 border-slate-200 hover:shadow-md
            rounded-full px-2 py-1 text-xs"
          >
            Previous Period
            <div>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="2"
                stroke="currentColor"
                class="w-4 h-4 text-cyan-500"
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
