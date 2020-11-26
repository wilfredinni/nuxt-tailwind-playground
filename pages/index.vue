<template>
  <div>
    <!-- groups -->
    <div class="grid justify-center">
      <div
        class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 mt-4 gap-4"
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
    </div>

    <!-- <div class="container mx-auto text-center my-4">
      <div class="grid grid-cols-3 gap-4">
        <div class="bg-red-300">1</div>
        <div class="bg-blue-300">2</div>
        <div class="bg-green-200">3</div>
        <div class="bg-gray-300">4</div>
        <div class="bg-orange-300 col-span-2">5</div>
        <div class="bg-red-300 col-span-3">6</div>
        <div class="bg-blue-300">7</div>
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      elements: [
        { title: 'Ingresos', icon: 'mdi mdi-bank', color: 'teal' },
        { title: 'Ahorro', icon: 'mdi mdi-piggy-bank', color: 'blue' },
        { title: 'Comida', icon: 'mdi mdi-food-apple', color: 'red' },

        { title: 'Social', icon: 'mdi mdi-glass-mug-variant', color: 'red' },
        { title: 'Viajes', icon: 'mdi mdi-airplane', color: 'red' },
      ],
    }
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
