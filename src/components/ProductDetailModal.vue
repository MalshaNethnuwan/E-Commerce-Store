<template>
  <div class="fixed inset-0 bg-black/40 flex justify-center items-center">
    <div class="bg-white p-6 w-96 rounded-lg">
      <img :src="product.thumbnail" class="w-full rounded"/>
      <h1 class="text-2xl font-bold mt-2">{{ product.title }}</h1>
      <p>{{ product.description }}</p>
      <p class="text-pink-500 font-bold mt-2">${{ product.price }}</p>

      <button @click="addToCart(product)" class="bg-pink-600 text-white px-4 py-2 rounded mt-3">
        Add to Cart
      </button>

      <button @click="$emit('close')" class="mt-3 underline">Close</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { Product } from "../interfaces/Product";
import { useCartStore } from "../store/cartStore";

const props = defineProps<{ product: Product }>();
const emit = defineEmits(["close"]);

const cart = useCartStore();

function addToCart(p: Product) {
  cart.addToCart(p);
}
</script>