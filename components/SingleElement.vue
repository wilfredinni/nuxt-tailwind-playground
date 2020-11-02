<template>
  <div
    class="rounded-2xl py-4 transition duration-300 hover:bg-gray-200 w-40 cursor-pointer"
    @mouseover="showActions()"
    @mouseleave="hideActions()"
  >
    <div v-click-outside="deactivateOver" class="relative">
      <div class="absolute ml-8 pt-2">
        <div
          class="transition duration-300 w-24 flex justify-between"
          :class="actionClass"
        >
          <!-- star -->
          <div
            class="rounded transition duration-300"
            :class="`hover:bg-${color}-400`"
            @click=";(fave = !fave), $emit('fave-action')"
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
          <AppDropdown>
            <template slot="toggler">
              <div
                class="rounded transition duration-300"
                :class="`hover:bg-${color}-400`"
                @click="alwaysOn = true"
              >
                <span class="mdi mdi-dots-horizontal text-white mx-1 my-2" />
              </div>
            </template>
            <AppDropdownContent>
              <AppDropdownItem @click.native="deactivateOver()">
                Action 1
              </AppDropdownItem>
              <AppDropdownItem @click.native="deactivateOver()">
                Action 2
              </AppDropdownItem>
              <AppDropdownItem @click.native="deactivateOver()">
                Action 3
              </AppDropdownItem>
            </AppDropdownContent>
          </AppDropdown>
        </div>
      </div>
    </div>

    <div
      class="flex items-center justify-center rounded-2xl mx-auto h-32 w-32"
      :class="`bg-${color}-500`"
      @click="$emit('action')"
    >
      <span class="text-white text-6xl" :class="icon" />
    </div>

    <!-- title -->
    <div class="flex items-center justify-center">
      <p class="text-sm pt-2" v-text="title" />
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
      alwaysOn: false,
      actionClass: 'opacity-0',
      fave: false,
    }
  },
  methods: {
    showActions() {
      this.actionClass = 'opacity-1'
    },
    hideActions() {
      if (!this.alwaysOn) this.actionClass = 'opacity-0'
    },
    deactivateOver() {
      this.alwaysOn = false
      this.hideActions()
    },
  },
}
</script>

<style></style>
