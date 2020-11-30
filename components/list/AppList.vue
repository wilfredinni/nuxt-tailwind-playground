<template>
  <div>
    <div
      class="flex justify-between items-center rounded-xl hover:bg-gray-200 px-3 py-3 cursor-pointer"
      @mouseover="showHiddenFields()"
      @mouseleave="hideHiddenFields()"
    >
      <div class="flex items-center">
        <!-- icon -->
        <div
          class="mr-3 h-10 w-10 rounded-lg items-center flex justify-center"
          :class="`bg-${item.color}-500`"
        >
          <span class="text-2xl" :class="`${item.icon} text-white`" />
        </div>

        <!-- title and date -->
        <div>
          <p class="text-sm">{{ item.title }}</p>
          <p class="text-gray-600 text-xs">{{ item.dueDate }}</p>
        </div>
      </div>

      <!-- amount -->
      <div :class="actionClass" class="transition duration-300">
        <p class="text-sm text-gray-700">${{ item.amount }}</p>
      </div>
      <div>
        <img src="/carlos.jpg" width="28" class="rounded-full ml-3" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppList',
  props: {
    item: {
      type: Object,
      default() {
        return {}
      },
    },
  },
  data() {
    return {
      actionClass: 'opacity-0',
    }
  },
  methods: {
    showHiddenFields() {
      this.actionClass = 'opacity-1'
    },
    hideHiddenFields() {
      if (!this.alwaysOn) this.actionClass = 'opacity-0'
    },
  },
}
</script>

<style></style>
