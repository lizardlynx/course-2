<template>
  <div>
    <button @click="buttonClicked">-</button>
  </div>
</template>

<script>
import Vue from 'vue'
import Component from 'nuxt-class-component'
import { Emit } from 'vue-property-decorator'

@Component({})

export default class ButtonPlus extends Vue {
  @Emit('minus')
  buttonClicked() {
    return;
  }
}
</script>

<style scoped>
button {
  background-color: red;
  width: 50px;
  height: 50px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
}
</style>