<template>
  <div>
    <h2>Fruit Object</h2>
    <ul>
      <li v-for="(fruit, country) in fruitObject" :key="country">{{ country }} : {{ fruit }}</li>
    </ul>
  </div>
</template>

<script>
import Vue from 'vue'
import Component from 'nuxt-class-component'

@Component({
  props: ['fruitObject']
})

export default class FruitList extends Vue{
  
}
</script>

<style scoped>
div, ul {
  margin: 40px;
}
</style>