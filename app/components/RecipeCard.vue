<script setup lang="ts">
import { type Recipe } from "../../types/types";

defineProps<{
  recipe: Recipe;
}>();
</script>

<template>
  <div class="flex flex-col shadow rounded-md">
    <NuxtImg
      :src="recipe.image"
      sizes="xs:100vw sm:50vw lg:400px"
      format="webp"
      densities="x1"
      alt=""
      class="rounded-t-md"
    />
    <div class="flex flex-col py-6 px-4 flex-1">
      <p class="text-xl lg:text-xl font-semibold mb-2">{{ recipe.name }}</p>
      <div
        class="font-normal w-full bg-white/80 flex gap-8 text-lg mb-4 mt-auto"
      >
        <div class="flex items-center gap-1">
          <Icon name="mdi:clock-time-eight-outline" class="text-yellow-500" />
          <span>{{ recipe.cookTimeMinutes }}</span>
        </div>
        <div class="flex items-center gap-1">
          <Icon name="mdi:fire" class="text-yellow-500" />
          <span>{{ recipe.caloriesPerServing }}</span>
        </div>
        <div class="flex items-center gap-1">
          <Icon name="mdi:star" class="text-yellow-500" />
          <span>{{ recipe.rating }} ({{ recipe.reviewCount }})</span>
        </div>
      </div>
      <BaseBtn :to="`/recipes/${recipe.id}`" label="View" />
    </div>
  </div>
</template>
