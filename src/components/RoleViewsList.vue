<script setup lang="ts">
import DataModel from '@/components/DataModel.vue';
const props = defineProps<{
  views: { id: number; name: string }[];
}>();
</script>

<template>
  <div class="flex flex-col m-4 gap-4">
    <p>Selected views</p>
    <div class="flex flex-col gap-2">
      <DataModel v-for="view in props.views" :key="view.id" :id="view.id" :name="view.name"/>
    </div>
  </div>
</template>