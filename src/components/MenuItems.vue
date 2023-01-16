<script>
export default {
  props: {
    name: String,
    active: Boolean,
    icon: null,
  },
};
</script>

<template>
  <div
    :class="[
      'flex space-x-2 my-1 items-center rounded-full px-2 py-2 w-full hover:bg-cyan-100',
      {
        'bg-cyan-50 font-semibold': active,
      },
    ]"
  >
    <component :is="icon" v-if="icon" class="h-5 w-5" />
    <button class="rounded-md text-left text-sm">
      {{ name }}
    </button>
  </div>
</template>
