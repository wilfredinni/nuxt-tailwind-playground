<template>
  <div>
    <div class="flex flex-col min-h-screen">
      <div class="flex">
        <div class="bg-gray-700 w-64 flex-none overflow-y-auto hidden lg:block">
          <div class="flex px-4 justify-between h-16">
            <div class="flex items-center">
              <img src="/grudget.png" width="30" alt="" />
              <h1 class="text-lg text-gray-300 font-medium ml-2">Grudget</h1>
            </div>
            <div class="flex items-center">
              <span class="mdi text-gray-400 mdi-menu text-2xl"></span>
            </div>
          </div>
        </div>

        <div class="flex flex-1 items-center justify-between h-16 px-8">
          <!-- inicio -->
          <h2 class="text-xl">Inicio</h2>

          <div class="flex">
            <!-- search -->
            <div class="relative items-center text-gray-600 hidden sm:block">
              <input
                type="search"
                name="search"
                placeholder="Search"
                class="focus:border-blue-500 focus:outline-none w-full text-sm text-black placeholder-gray-500 border border-gray-400 rounded-md pl-4 py-2 pr-10"
              />
              <span
                class="mdi mdi-magnify text-xl absolute right-0 mr-4 mt-1"
              />
            </div>

            <!-- plus -->
            <div>
              <button
                class="p-0 w-8 h-8 bg-orange-500 rounded-full hover:bg-orange-600 active:shadow-lg shadow transition ease-in duration-200 focus:outline-none ml-3"
              >
                <span class="mdi mdi-plus text-xl font-bold text-white" />
              </button>
            </div>

            <!-- avatar -->
            <div>
              <img
                src="/carlos.jpg"
                width="33"
                class="rounded-full ml-3"
                alt=""
              />
            </div>
          </div>
        </div>
      </div>

      <div class="flex-1 flex">
        <div class="bg-gray-700 w-64 flex-none overflow-y-auto hidden lg:block">
          <side-bar></side-bar>
        </div>
        <div class="flex-1">
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SideBar from '~/components/layout/SideBar.vue'
export default {
  components: { SideBar },
}
</script>

<style></style>
