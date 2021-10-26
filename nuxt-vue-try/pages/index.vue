<template>
  <div>
    <fruit-list :fruit-array="fruitArray"/>
    <fruit-object :fruit-object="fruitObject"/>
    <div class="counter-container">
      <div><button-plus v-if="count < 20" @plus="plus"/></div>
      <counter :count="count" v-bind:class="[count%3 === 0 ? 'redText' : '', count%5 === 0 ? 'greenText' : '']"/>
      <div><button-minus v-if="count > 0" @minus="minus"/></div>
    </div>
    <counter-input @counterInputSubmit="counterInputSubmit"/>
  </div>
</template>

<script>
import Vue from 'vue'
import Component from 'nuxt-class-component'
import ButtonMinus from '../components/ButtonMinus.vue'
import ButtonPlus from '../components/ButtonPlus.vue'
import Counter from '../components/Counter.vue' 
import FruitList from '../components/FruitList.vue'
import FruitObject from '../components/FruitObject.vue'
import CounterInput from '../components/CounterInput.vue'
@Component({
  components: {
    Counter,
    ButtonPlus,
    ButtonMinus,
    FruitList,
    FruitObject,
    CounterInput
  }
})

export default class IndexPage extends Vue {
  fruitArray = ['apple', 'pineapple', 'mango', 'melon'];
  fruitObject = {'Canada': 'Apple', 'Ukraine': 'Mango', 'China': 'Raspberry'}
  count = 0;

  plus() {
    if (this.count < 20) this.count++;
  }

  minus() {
    if (this.count > 0) this.count--;
  }

  counterInputSubmit(value) {
    if (value) this.count = value;
  }
}
</script>

<style>
.counter-container {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}

.counter-container > div:nth-child(1),
.counter-container > div:nth-child(3) {
  width: 50px;
}

.redText {
  color: red;
}

.greenText {
  color: green;
}

</style>
