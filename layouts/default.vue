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
        <div class="flex flex-1 justify-between items-center px-8">
          <div>
            <h2 class="text-xl">Inicio</h2>
          </div>
          <div class="flex items-center mt-2 mb-6">
            <div class="relative text-gray-600">
              <input
                type="search"
                name="search"
                placeholder="Search"
                class="border h-10 px-5 pr-10 rounded-full text-sm focus:outline-none"
              />
              <button type="submit" class="absolute right-0 top-0 mt-3 mr-4">
                <span class="mdi mdi-magnify text-xl"></span>
              </button>
            </div>
            <img
              src="/carlos.jpg"
              width="35"
              class="rounded-full ml-3"
              alt=""
            />
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
