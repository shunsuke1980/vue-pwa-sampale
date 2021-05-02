<template>
  <div class="hello">
    <div>
      <input min="0" type="number" step="1" v-model="appleNum">
    </div>
    <div>
      <input min="0" type="number" step="1" v-model="applePrice">
    </div>
    <div>
      <input type="button" class="button" value="Calc" @click="calculation">
    </div>
    <div>
      {{ appleSum }}
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const appleNum = ref<number>(5);
    const applePrice = ref<number>(6);
    const appleSum = ref<number>(30);
    const calculation = () => {
      appleSum.value = appleNum.value * applePrice.value;
    };
    return {
      appleNum,
      applePrice,
      appleSum,
      calculation,
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
div {
  margin: 5px;
  font-size: 1.5em;
}
input {
  font-size: 1.1em;
  width: 2.5em;
}
input.button {
  color: #42b983;
}
</style>
