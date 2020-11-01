<template>
  <div class="container mx-auto flex mt-10">
    <single-element
      v-for="item in elements"
      :key="item.title"
      :title="item.title"
      :icon="item.icon"
      :color="item.color"
      class="mx-2"
      @action="clickAction()"
      @fave-action="faveUnFave()"
    />
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
