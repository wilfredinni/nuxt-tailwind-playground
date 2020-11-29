<template>
  <div>
    <!-- groups -->
    <div class="grid justify-center">
      <div class="border-b-2 mb-3 flex items-center mx-2">
        <span class="mdi mdi-menu-down text-2xl text-gray-700" />
        <p>Favoritos</p>
      </div>

      <div
        class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-4"
      >
        <div v-for="(item, index) in elements" :key="index">
          <single-element
            :title="item.title"
            :icon="item.icon"
            :color="item.color"
            @action="clickAction()"
            @fave-action="faveUnFave()"
          />
        </div>
      </div>

      <!-- pending movements -->
      <div class="border-b-2 mb-3 flex items-center mx-2 mt-10">
        <span class="mdi mdi-menu-down text-2xl text-gray-700" />
        <p>Movimientos pendientes</p>
      </div>
      <div class="mx-2">
        <div
          v-for="(item, index) in urgentMovements"
          :key="index"
          class="flex justify-between items-center hover:bg-gray-200 px-3 py-3 cursor-pointer"
          @mouseover="showHiddenFields()"
          @mouseleave="hideHiddenFields()"
        >
          <div class="flex items-center">
            <!-- icon -->
            <div
              class="mr-3 h-10 w-10 rounded-lg items-center flex justify-center"
              :class="`bg-${item.color}-500`"
            >
              <span class="text-2xl" :class="`${item.icon} text-white`" />
            </div>

            <!-- title and date -->
            <div>
              <p class="text-sm">{{ item.title }}</p>
              <p class="text-gray-600 text-xs">{{ item.dueDate }}</p>
            </div>
          </div>

          <!-- amount -->
          <div :class="actionClass" class="transition duration-300">
            <p class="text-sm text-gray-700">${{ item.amount }}</p>
          </div>
          <div>
            <img
              src="/carlos.jpg"
              width="28"
              class="rounded-full ml-3"
              alt=""
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      actionClass: 'opacity-0',
      elements: [
        { title: 'Ingresos', icon: 'mdi mdi-bank', color: 'teal' },
        { title: 'Ahorro', icon: 'mdi mdi-piggy-bank', color: 'blue' },
        { title: 'Comida', icon: 'mdi mdi-food-apple', color: 'red' },
        { title: 'Social', icon: 'mdi mdi-glass-mug-variant', color: 'red' },
        { title: 'Viajes', icon: 'mdi mdi-airplane', color: 'red' },
      ],
      urgentMovements: [
        {
          title: 'Arriendo',
          icon: 'mdi mdi-bank-plus',
          amount: '250.000',
          color: 'teal',
          dueDate: 'Lunes 13 de agosto de 2021',
        },
        {
          title: 'Matrimonio',
          icon: 'mdi mdi-piggy-bank',
          amount: '200.000',
          color: 'blue',
          dueDate: 'Lunes 13 de agosto de 2021',
        },
        {
          title: 'Supermercado',
          icon: 'mdi mdi-food-apple',
          amount: '80.000',
          color: 'red',
          dueDate: 'Lunes 13 de agosto de 2021',
        },
        {
          title: 'Arriendo',
          icon: 'mdi mdi-home',
          amount: '230.000',
          color: 'red',
          dueDate: 'Lunes 13 de agosto de 2021',
        },
        {
          title: 'Luz',
          icon: 'mdi mdi-home',
          amount: '16.000',
          color: 'red',
          dueDate: 'Lunes 13 de agosto de 2021',
        },
      ],
    }
  },
  methods: {
    showHiddenFields() {
      this.actionClass = 'opacity-1'
    },
    hideHiddenFields() {
      if (!this.alwaysOn) this.actionClass = 'opacity-0'
    },
    clickAction() {
      alert('Card Clicked')
    },
    faveUnFave() {
      // alert('Fave or un fave')
    },
  },
}
</script>

<style></style>
