<template>
  <div
    class="border rounded-lg p-3 shadow hover:scale-105 transition cursor-pointer"
    @click="$emit('select', product)"
  >
    <img :src="product.thumbnail" class="w-full h-40 object-cover" />
    <h2 class="font-semibold mt-2">{{ product.title }}</h2>
    <p class="text-pink-600 font-bold">${{ product.price }}</p>
  </div>
</template>

<script setup lang="ts">
import type { Product } from "../interfaces/Product";

defineProps<{ product: Product }>();
defineEmits(["select"]);
</script>