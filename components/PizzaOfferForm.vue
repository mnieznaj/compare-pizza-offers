<template>
  <form @submit.prevent="$emit('addPizzaOffer', pizzaOffer)" class="flex flex-col w-96">
    <h2 class="font-medium text-4xl mb-4">Add pizza offer</h2>

    <label>Offer name</label>
    <input v-model="pizzaOffer.name" type="text" class="border border-1 border-black my-4"/>
    <label>Price</label>
    <input v-model.number="pizzaOffer.price" type="text" class="border border-1 border-black my-4"/>
    <label>Quantity</label>
    <input v-model.number="pizzaOffer.quantity" type="text" class="border border-1 border-black my-4"/>
    <label>Diameter</label>
    <input v-model.number="pizzaOffer.diameter" type="text" class="border border-1 border-black my-4"/>

    <button type="submit" class="border border-black my-4">Add pizza offer</button>
  </form>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import {PizzaOffer} from "~/types/types";

const emits = defineEmits(['addPizzaOffer']);

const pizzaOffer = ref<PizzaOffer>({
  name: '',
  price: 0,
  quantity: 0,
  diameter: 0,
});

function addPizzaOffer() {
  emits('addPizzaOffer', pizzaOffer.value);
  pizzaOffer.value = {
    name: '',
    price: 0,
    quantity: 0,
    diameter: 0,
  };
}
</script>
