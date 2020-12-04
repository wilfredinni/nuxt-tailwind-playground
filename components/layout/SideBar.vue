<template>
  <div>
    <!-- principal -->
    <div class="px-2">
      <nuxt-link
        v-for="item in items"
        :key="item.title"
        class="flex items-center p-2 my-3 rounded-lg cursor-pointer"
        :class="isActive(item)"
        :to="item.link"
        nuxt
      >
        <span v-html="item.icon" />
        <p class="text-gray-200 font-medium text-sm">{{ item.title }}</p>
      </nuxt-link>

      <!-- budgets -->
      <template>
        <div class="border-b border-gray-600"></div>
        <div class="flex items-center p-2 mt-2 justify-between">
          <p class="text-gray-200 font-medium text-sm">Presupuestos</p>
          <span class="mdi mdi-plus text-white"></span>
        </div>

        <!-- budget items -->
        <div class="flex items-center">
          <div class="w-2 h-2 ml-3 mr-4 my-3 bg-yellow-400 rounded-sm"></div>
          <p class="text-gray-200 font-medium text-sm">Básicos</p>
        </div>
        <div class="flex items-center">
          <div class="w-2 h-2 ml-3 mr-4 my-3 bg-red-400 rounded-sm"></div>
          <p class="text-gray-200 font-medium text-sm">Entretenimiento</p>
        </div>
        <div class="flex items-center">
          <div class="w-2 h-2 ml-3 mr-4 my-3 bg-teal-400 rounded-sm"></div>
          <p class="text-gray-200 font-medium text-sm">Navidad</p>
        </div>
      </template>

      <!-- Projects -->
      <template>
        <div class="border-b border-gray-600 mt-3"></div>
        <div class="flex items-center p-2 mt-2 justify-between">
          <p class="text-gray-200 font-medium text-sm">Proyectos</p>
          <span class="mdi mdi-plus text-white"></span>
        </div>

        <!-- projects items -->
        <div class="flex items-center">
          <div class="w-2 h-2 ml-3 mr-4 my-3 bg-blue-400 rounded-sm"></div>
          <p class="text-gray-200 font-medium text-sm">Jabones Cucao</p>
        </div>
        <div class="flex items-center">
          <div class="w-2 h-2 ml-3 mr-4 my-3 bg-orange-400 rounded-sm"></div>
          <p class="text-gray-200 font-medium text-sm">Pago CAE</p>
        </div>
        <div class="flex items-center">
          <div class="w-2 h-2 ml-3 mr-4 my-3 bg-purple-400 rounded-sm"></div>
          <p class="text-gray-200 font-medium text-sm">Matrimonio</p>
        </div>
      </template>
    </div>

    <!-- User -->
    <div class="absolute bottom-0 flex flex-col w-64">
      <div class="border-b border-gray-600"></div>
      <div class="flex justify-between items-center px-4 py-4">
        <div class="flex items-center">
          <img src="/carlos.jpg" width="33" class="rounded-full" alt="" />
          <div class="ml-3">
            <p class="text-gray-300 font-medium text-sm">Carlos Montecinos</p>
            <p class="text-gray-400 font-medium text-xs">Ver perfil</p>
          </div>
        </div>
        <div>
          <span class="mdi mdi-cog text-gray-400 text-xl"></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'Inicio',
          link: '/',
          name: 'index',
          icon: `<svg
            class="w-6 h-6 mr-4 text-gray-500"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
            ></path>
          </svg>`,
        },
        {
          title: 'Movimientos',
          link: '/movements',
          name: 'movements',
          icon: `<svg
            class="w-6 h-6 mr-4 text-gray-500"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"
            ></path>
          </svg>`,
        },
        {
          title: 'Reportes',
          link: '/',
          name: 'reports',
          icon: `<svg
            class="w-6 h-6 mr-4 text-gray-500"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
            ></path>
          </svg>`,
        },
      ],
    }
  },
  methods: {
    isActive(item) {
      if (this.$route.name === item.name) return 'bg-gray-800'
      return 'hover:bg-gray-800 hover:bg-opacity-25'
    },
  },
}
</script>

<style></style>
