<template>
 
  <div>
    <h1>Price: ${{price}}</h1>
    <button @click="makeOrder">Make next order</button>
    <p>Quantity: {{ quantity }}</p>
    <p>Oreder total price: {{ totalPrice }}</p>
    <p>Tax: {{ tax }}</p>
  </div>
</template>

<script>

import { 
   ref, 
  // reactive,
  // toRefs,
  computed
  } from 'vue'

export default {
  name: "MyMainComponent",
  setup() {
    const quantity = ref(0)
    const price = ref(100)
    const totalPrice = computed( ()=> price.value * quantity.value )
    const tax = computed(()=> totalPrice.value * 0.23)

    function makeOrder() {
      quantity.value++;
    }

    // const state = reactive({
    //   quantity: 0,
    //   price: 100,
    //   totalPrice: 0,
    //   tax: 0

    // })

    // function makeOrder() {
    //   state.quantity++;
    //   state.totalPrice = state.quantity * state.price
    //   state.tax = state.totalPrice * 0.23;
    // }
      
    return { makeOrder, quantity, price, totalPrice, tax }
    // return { makeOrder, ...toRefs(state) }
    }
};
</script>


