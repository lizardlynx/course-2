<template>
  <div>
    <h2>Fruit Array</h2>
    <ul>
      <li v-for="(fruit, id) in fruitArray" :key="id">{{ id }} : {{ fruit }}</li>
    </ul>
  </div>
</template>

<script>
import Vue from 'vue'
import Component from 'nuxt-class-component'

@Component({
  props: ['fruitArray']
})

export default class FruitList extends Vue{
  
}
</script>

<style scoped>
div, ul {
  margin: 40px;
}
</style>
