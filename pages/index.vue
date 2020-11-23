<template>
  <div>
    <div class="grid justify-center mt-10">
      <!-- title and divider -->
      <div class="container">
        <div class="grid grid-cols-5 gap-2">
          <!-- <div class="col-span-4 bg-green-300"></div> -->
          <div class="col-span-5 bg-green-300">i</div>
          <!-- <div class="col-span-1 bg-green-300"></div> -->
        </div>
      </div>
    </div>

    <!-- groups -->
    <div class="grid justify-center mt-10">
      <div
        v-if="showFaves"
        class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-5 mt-4 gap-2"
      >
        <div v-for="item in elements" :key="item.title">
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
  </div>
</template>

<script>
export default {
  data() {
    return {
      showFaves: true,
      elements: [
        { title: 'Ingresos', icon: 'mdi mdi-bank', color: 'teal' },
        { title: 'Ahorro', icon: 'mdi mdi-piggy-bank', color: 'blue' },
        { title: 'Comida', icon: 'mdi mdi-food-apple', color: 'red' },
        { title: 'Social', icon: 'mdi mdi-glass-mug-variant', color: 'red' },
        { title: 'Viajes', icon: 'mdi mdi-airplane', color: 'red' },
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
