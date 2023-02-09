<template>
  <div>
    <h2 class="text-4xl font-bold mb-8">Collected pizza offers</h2>
    <div>
      <PizzaOffer
        v-for="pizzaOffer in pizzaOffers"
        :key="pizzaOffer.name"
        :pizzaOffer="pizzaOffer"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { PizzaOffer as PizzaOfferType } from "~/types/types";
import PizzaOffer from "~/components/PizzaOffer.vue";

defineProps<{
  pizzaOffers: PizzaOfferType[];
}>();
</script>
