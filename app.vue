<template>
  <div class="p-24">
    <h1 class="font-bold text-6xl mb-4">Compare pizza offers online</h1>
    <p class="mb-16">Check which pizza offer has more pizza for less $</p>
    <div class="flex gap-x-12">
      <div>
        <PizzaOfferForm @addPizzaOffer="addPizzaOffer"/>
      </div>

      <div>
        <CollectedPizzaOffers :pizzaOffers="pizzaOffers"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { PizzaOffer} from "~/types/types";
import PizzaOfferForm from "~/components/PizzaOfferForm.vue";
import CollectedPizzaOffers from "~/components/CollectedPizzaOffers.vue";

const pizzaOffers = ref<PizzaOffer[]>([]);

const addPizzaOffer = (pizzaOffer: PizzaOffer) => {
  pizzaOffers.value.push({...pizzaOffer});
  console.log('pizzaOffers', pizzaOffers.value)
};
</script>
