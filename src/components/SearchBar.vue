<template>
  <input
    v-model="search"
    type="text"
    placeholder="Search makeup..."
    class="px-4 py-2 border rounded w-full"
    @input="$emit('update:modelValue', search)"
  />
</template>

<script setup lang="ts">
import { ref } from "vue";
const search = ref("");
</script>