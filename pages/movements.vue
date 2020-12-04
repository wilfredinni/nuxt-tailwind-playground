<template>
  <div class="flex border-t">
    <!-- movements -->
    <div class="flex flex-col w-4/6">
      <!-- title -->
      <div class="flex flex-1 border-b justify-between py-6 px-8">
        <h1 class="text-2xl font-medium">Movimientos</h1>

        <button
          class="border-gray-400 border-2 flex items-center p-2 px-4 rounded-lg"
        >
          <!-- icon -->
          <svg
            class="w-6 h-6 text-gray-500 mr-1"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M3 3a1 1 0 000 2h11a1 1 0 100-2H3zM3 7a1 1 0 000 2h5a1 1 0 000-2H3zM3 11a1 1 0 100 2h4a1 1 0 100-2H3zM13 16a1 1 0 102 0v-5.586l1.293 1.293a1 1 0 001.414-1.414l-3-3a1 1 0 00-1.414 0l-3 3a1 1 0 101.414 1.414L13 10.414V16z"
            ></path>
          </svg>

          <!-- text -->
          <span class="font-medium text-gray-800 text-sm">Filtrar</span>

          <!-- down -->
          <svg
            class="w-6 h-6 text-gray-500 ml-1"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </button>
      </div>

      <div class="">
        <!-- start -->
        <!-- <div class="flex flex-col items-center border-b">
          <div class="flex items-center">
            <span class="w-2 h-2 rounded-full bg-red-400"></span>
            <p>Arriendo</p>
          </div>
          <p>sdfsdf</p>
        </div> -->
        <div
          v-for="item in movements"
          :key="item.name"
          class="flex flex-1 border-b"
        >
          <div class="flex justify-between flex-1 px-8">
            <div class="flex items-center">
              <div class="w-2 h-2 ml-3 mr-4 my-3 bg-red-500 rounded-full"></div>
              <p class="text-sm">{{ item.name }}</p>
            </div>
            <div class="flex items-center">
              <div class="mr-10 text-gray-600 text-sm">Editar</div>
              <span
                class="mdi mdi-star text-xl"
                :class="{
                  'text-orange-400': item.favorite,
                  'text-gray-400': !item.favorite,
                }"
              ></span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- additional -->
    <div class="flex-1 hidden lg:block border-l"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movements: [
        {
          name: 'Arriendo',
          color: 'red',
          amount: '240.000',
          date: '25 de enero de 2021',
          favorite: true,
        },
        {
          name: 'Matrimonio',
          color: 'blue',
          amount: '200.000',
          date: '30 de enero de 2021',
          favorite: false,
        },
      ],
    }
  },
}
</script>

<style></style>
