<template>
  <div class="flex justify-center">
    <div class="flex flex-col lg:w-5/6" :class="columnSize">
      <!-- groups -->
      <div class="border-b-2 mb-3 mt-3 flex items-center mx-2">
        <span class="mdi mdi-menu-down text-2xl text-gray-700" />
        <p>Favoritos</p>
      </div>

      <div
        class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 xl:grid-cols-5"
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
        <app-list
          v-for="(item, index) in urgentMovements"
          :key="index"
          :item="item"
        />
      </div>
    </div>
    <!-- <notification :type="'success'">
      <notification-title>Successfully saved!</notification-title>
      <notification-msg>
        Anyone with a link can now view this file.
      </notification-msg>
    </notification> -->
  </div>
</template>

<script>
// import Notification from '../components/notification/Notification.vue'

export default {
  // components: { Notification },
  data() {
    return {
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
      colors: [
        'gray',
        'yellow',
        'orange',
        'red',
        'green',
        'teal',
        'blue',
        'indigo',
        'purple',
        'pink',
      ],
      sizes: ['lg', 'md', 'sm'],
    }
  },
  computed: {
    columnSize() {
      if (this.elements.length > 0) return 'xl:w-auto'
      return 'xl:w-2/4'
    },
  },
  methods: {
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
