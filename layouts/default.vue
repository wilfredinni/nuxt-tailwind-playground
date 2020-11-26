<template>
  <div>
    <div class="grid">
      <div
        class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-12 gap-2"
      >
        <!-- sidebar -->
        <div
          class="bg-green-200 col-span-2 h-screen overflow-y-auto hidden lg:block"
        ></div>

        <!-- app -->
        <div
          class="bg-red-200 col-span-12 lg:col-span-10 h-screen overflow-y-auto"
        >
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
