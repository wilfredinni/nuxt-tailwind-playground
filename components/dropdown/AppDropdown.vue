<template>
  <div v-click-outside="away" class="relative" @click="toggle">
    <slot name="toggler">
      <button>Toggle</button>
    </slot>
    <slot />
  </div>
</template>

<script>
export default {
  name: 'AppDropdown',
  provide() {
    return {
      sharedState: this.sharedState,
    }
  },
  data() {
    return {
      sharedState: {
        active: false,
      },
    }
  },
  methods: {
    toggle() {
      this.sharedState.active = !this.sharedState.active
    },
    away() {
      this.sharedState.active = false
    },
  },
}
</script>
