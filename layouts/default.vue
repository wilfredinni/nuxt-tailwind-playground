<template>
  <div>
    <div class="flex flex-col min-h-screen">
      <div class="flex">
        <div class="bg-gray-700 w-56 flex-none overflow-y-auto hidden lg:block">
          <div class="flex px-4 justify-between h-16">
            <div class="flex items-center">
              <img src="/grudget.png" width="30" alt="" />
              <h1 class="text-lg text-gray-300 font-semibold ml-2">Grudget</h1>
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
            <div class="relative flex items-center text-gray-600">
              <input
                type="search"
                name="search"
                placeholder="Search"
                class="border h-10 px-5 pr-10 rounded-full text-sm focus:outline-none"
              />
              <span
                class="mdi mdi-magnify text-xl absolute right-0 mr-4"
              ></span>
            </div>

            <!-- plus -->
            <div>
              <button
                class="p-0 w-8 h-8 bg-orange-500 rounded-full hover:bg-orange-700 active:shadow-lg shadow transition ease-in duration-200 focus:outline-none ml-3"
              >
                <span class="mdi mdi-plus text-xl font-bold text-white"></span>
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
        <div class="bg-gray-700 w-56 flex-none overflow-y-auto hidden lg:block">
          sidebar
        </div>
        <div class="flex-1">
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
