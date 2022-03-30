<template>
  <div class="grid">
    <input v-model="result" placeholder="0" />
    <button
      @click="inputValue(num)"
      class="cell num"
      type="text"
      v-for="num in numbers"
      :key="num.index"
    >
      {{ num }}
    </button>
    <button
      @click="inputValue(op)"
      class="cell op"
      v-for="op in operations"
      :key="op.index"
    >
      {{ op }}
    </button>
    <button @click="resetValue" class="cell op">C</button>
    <button @click="calcValue" class="cell op">=</button>
    <button @click="squard" class="cell op">√x</button>
    <button @click="pow" class="cell op">x²</button>
    <button @click="cos" class="cell op">cos</button>
    <button @click="sin" class="cell op">sin</button>
    <button @click="tan" class="cell op">tan</button>
    <button @click="random" class="cell op">rand</button>
    <button @click="randomIntegers" class="cell op">randInt</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    
    const result = ref('');
    const numbers = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]);
    const operations = ref(["+", "-", "*", "/"]);

    const inputValue = (x) => {
      result.value = result.value.toString();
      result.value += x;
    };
    const resetValue = () => {
      result.value = "";
    };
    const calcValue = () => {
      result.value = eval(result.value);
    };
    const squard = () => {
      result.value = Math.sqrt(result.value);
    };
    const pow = () => {
      result.value = Math.pow(result.value, 2);
    };
    const cos = () => {
      result.value = Math.cos(result.value)
    };
    const sin = () => {
      result.value = Math.sin(result.value)
    };
    const tan = () => {
      result.value = Math.tan(result.value)
    }
    const randomIntegers = () => {
      result.value = Math.round(Math.random()*result.value)
    }
    const random = () => {
      result.value = Math.random()*result.value
    }

    return {
      result,
      numbers,
      operations,
      inputValue,
      resetValue,
      calcValue,
      squard,
      pow,
      cos,
      sin,
      tan,
      random,
      randomIntegers,
    };
  },
};
</script>

<style scoped>
input {
  width: 400px;
  border: 0;
  color: #243849;
  font-size: 20px;
  padding: 5px 5px;
  text-align: right;
}

.cell {
  flex: 33%;
  height: 50px;
  font-size: 22px;
  border: none;
}
.num {
  background-color: #243849;
  color: #fff;
  font-weight: 400;
}

.cell:hover {
  background-color: #182530;
  color:#fff;
}

.cell:active {
  background-color: #395e7a;
}

.op {
  background-color: #ff9900;
  color: #243849;
}
</style>