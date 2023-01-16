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
import { markRaw } from "vue";

export default {
  name: "Sidebar",
  data() {
    return {
      markRaw,

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

<template>
  <div class="px-3 py-2 border-r-[1px]">
    <!-- 1 section -->
    <div>
      <div class="text-2xl font-bold text-center">BlueReceipt</div>
      <div>
        <SidebarSearch />
      </div>
      <div class="m-2">
        <MenuItems active name="Dashboard" :icon="home" />
      </div>
      <div>
        <MenuItems
          v-for="i in listOfMenuItemData"
          :name="i.name"
          :icon="markRaw(i.icon)"
        />
      </div>
    </div>
    <!-- 2 section -->
    <div class="flex mt-56 space-x-4">
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
</template>
