<template>
  <input class="text-field" type="text" placeholder="jane@example.com" />
</template>

<script>
export default {
  name: 'TextField',
}
</script>

<style scoped>
.text-field {
  @apply bg-white;
  @apply border;
  @apply border-gray-300;
  @apply rounded-lg;
  @apply py-2;
  @apply px-4;
  @apply block;
  @apply w-full;
  @apply appearance-none;
  @apply leading-normal;
}
.text-field:focus {
  @apply outline-none;
  @apply shadow-outline;
}
</style>
