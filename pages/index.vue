<template>
  <div class="flex justify-center">
    <div class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-5">
      <div v-for="item in elements" :key="item.title" class="mt-10">
        <single-element
          :title="item.title"
          :icon="item.icon"
          :color="item.color"
          class="mx-2"
          @action="clickAction()"
          @fave-action="faveUnFave()"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: '',
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
