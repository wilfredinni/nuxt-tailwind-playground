<template>
  <transition name="dropdown-content">
    <div
      v-if="active"
      class="origin-top-left absolute left-0 mt-0 w-48 bg-white rounded border py-1"
    >
      <slot />
    </div>
  </transition>
</template>

<script>
export default {
  name: 'AppDropdownContent',
  inject: ['sharedState'],
  computed: {
    active() {
      return this.sharedState.active
    },
  },
}
</script>

<style>
.dropdown-content-enter-active,
.dropdown-content-leave-active {
  transition: all 0.2s;
}
.dropdown-content-enter,
.dropdown-content-leave-to {
  opacity: 0;
  transform: translateY(-5px);
}
</style>
