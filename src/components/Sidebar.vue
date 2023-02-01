<template>
  <div class="flex justify-between flex-col h-full px-3 py-2 border-r-[1px]">
    <!-- 1 section -->
    <div>
      <div class="flex justify-center">
        
        <div class="w-full">
          <button
          @click="$emit('onClick')"
          class="flex px-3 py-2 text-slate-900"
          >
          <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6"
          >
          <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M3.75 5.25h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5m-16.5 4.5h16.5"
          />
        </svg>
      </button>
    </div>
      </div>
      <div :class="{ flex: isOpen, 'w-[225px]': isOpen }">
        <div class="w-full block lg:items-center lg:w-auto">
          <div v-if="isOpen" class="text-2xl font-bold text-center">
            BlueReceipt
          </div>
          <div>
            <SidebarSearch v-if="isOpen" />
          </div>
          <div>
            <MenuItems active name="Dashboard" :icon="home" :open="isOpen" />
          </div>
          <div>
            <MenuItems v-for="i in listOfMenuItemData" :name="i.name"
            :icon="i.icon" :open="isOpen" />
          </div>
          <!-- 2 section -->
          <div v-if="isOpen" class="flex space-x-4">
            <div>
              <img
                src="/assets/avatar-image.webp"
                alt="Avatar"
                class="h-14 rounded-full"
              />
            </div>
            <div>
              <div class="text-md font-bold">ABD Villers</div>
              <p class="text-slate-500">Store Name</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SidebarSearch from "./SidebarSearch.vue";
import MenuItems from "./MenuItems.vue";
import home from "../assets/icons/home.vue";
import conversations from "../assets/icons/conversations.vue";
import automation from "../assets/icons/automation.vue";
import campaign from "../assets/icons/campaigns.vue";
import popup from "../assets/icons/popup.vue";
import livechat from "../assets/icons/livechat.vue";
import segments from "../assets/icons/segments.vue";
import integrations from "../assets/icons/integrations.vue";

export default {
  name: "Sidebar",
  props: ["isOpen"],
  data() {
    return {
      home,
      listOfMenuItemData: [
        {
          name: "Conversations",
          icon: conversations,
        },
        {
          name: "Automations",
          icon: automation,
        },
        {
          name: "Campaigns",
          icon: campaign,
        },
        {
          name: "Popup",
          icon: popup,
        },
        {
          name: "Live Chat",
          icon: livechat,
        },
        {
          name: "Segments",
          icon: segments,
        },
        {
          name: "Integrations",
          icon: integrations,
        },
      ],
    };
  },
  components: {
    SidebarSearch,
    MenuItems,
  },
};
</script>
