<script setup lang="ts">
import type { Measure } from '~/dataProcessing/loadData';

const props = defineProps<{
  measure: Measure;
}>();

</script>

<template>
   <NuxtLink
    :to="`/category/${measure.categoryId}/measure/${measure.id}`"
  >
    <Card class="category-card">
      <template #header>
        <div class="category-card--header">
          <h2 class="category-card--title">{{ measure.additionalData?.short_title || measure.original['Action outline']['Action name'] }}</h2>
        </div>
      </template>
      <template #content>
        <p class="category-card--text">{{ measure.additionalData?.summary || measure.original['Action outline']['Action description'] }}</p>
      </template>
      <template #footer>
        <div class="category-card--footer">
          <span class="category-card--link">Mehr erfahren</span>
        </div>
      </template>
    </Card>
  </NuxtLink>
</template>

<style scoped>
@import "../CategoryCard/CategoryCard.css";
</style>
