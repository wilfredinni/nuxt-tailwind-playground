<template>
  <div class="flex">
    <div class="container mx-auto mt-10">
      <div
        class="rounded-2xl py-4 transition duration-300 hover:bg-gray-200 w-40 cursor-pointer"
        @mouseover="showActions()"
        @mouseleave="hideActions()"
      >
        <div class="relative">
          <div class="absolute ml-8 pt-2">
            <div
              class="transition duration-300 w-24 flex justify-between"
              :class="actionClass"
            >
              <!-- star -->
              <div
                class="rounded transition duration-300"
                :class="`hover:bg-${color}-400`"
                @click="fave = !fave"
              >
                <span
                  class="text-white mx-1 my-2"
                  :class="{
                    'mdi mdi-star': fave,
                    'mdi mdi-star-outline': !fave,
                  }"
                />
              </div>

              <!-- menu -->
              <div
                class="rounded transition duration-300"
                :class="`hover:bg-${color}-400`"
              >
                <span class="mdi mdi-dots-horizontal text-white mx-1 my-2" />
              </div>
            </div>
          </div>
        </div>

        <div
          class="flex items-center justify-center rounded-2xl mx-auto h-32 w-32"
          :class="`bg-${color}-500`"
        >
          <span class="text-white text-6xl" :class="icon" />
        </div>

        <!-- title -->
        <div class="flex items-center justify-center">
          <p class="text-sm pt-2" v-text="title" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SingleElement',
  props: {
    title: {
      type: String,
      default() {
        return 'Title'
      },
    },
    icon: {
      type: String,
      default() {
        return 'mdi mdi-pulse'
      },
    },
    color: {
      type: String,
      default() {
        return 'blue'
      },
    },
  },
  data() {
    return {
      actionClass: 'opacity-0',
      fave: false,
    }
  },
  methods: {
    showActions() {
      this.actionClass = 'opacity-1'
    },
    hideActions() {
      this.actionClass = 'opacity-0'
    },
  },
}
</script>

<style></style>
