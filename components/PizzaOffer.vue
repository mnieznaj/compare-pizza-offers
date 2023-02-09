<template>
  <div class="flex justify-end border p-4">
    <div class="border-r-1 mx-4 font-bold justify-self-start">{{ pizzaOffer.name }}</div>
    <div class="border-r-1 mx-4">price: {{pizzaOffer.price}}</div>
    <div class="border-r-1 mx-4">quantity: {{pizzaOffer.quantity}}</div>
    <div class="border-r-1 mx-4">diameter: {{pizzaOffer.diameter}}</div>
    <div class="border-r-1 mx-4">pizza cm^3/$: {{pizzaCm3PerDollar}}</div>
  </div>
</template>

<script lang="ts" setup>
import {PizzaOffer} from "~/types/types";

const props = defineProps<{
  pizzaOffer: PizzaOffer;
}>();

const pizzaCm3PerDollar = computed(() => {
  const radius = props.pizzaOffer.diameter / 2;
  const area = Math.PI * Math.pow(radius, 2);
  return (area / props.pizzaOffer.price).toFixed(2);
});
</script>
