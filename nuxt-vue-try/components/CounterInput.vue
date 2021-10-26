<template>
  <div>
    <input type="number" min="0" max="20" v-on:keyup.enter="submit" v-model="value">
  </div>
  
</template>

<script>
import Vue from 'vue';
import Component from 'nuxt-class-component'
import { Emit } from 'vue-property-decorator'

@Component({})

export default class CounterInput extends Vue {
  value = null;
  @Emit('counterInputSubmit')
  submit() {
    const val = +(this.value);
    if (!val) return null;
    else if (val > 20 || val < 0) return null;
    else {
      this.value = '';
      return val;
    }
  }
}
</script>

<style>
input {
  margin: 20px;
  background-color: white;
  border-radius: 20px;
  border: 1px solid gray;
  height: 50px;
  padding: 10px;
}
</style>
