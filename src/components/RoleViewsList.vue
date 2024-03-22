<script setup lang="ts">
const props = defineProps<{
  views: { id: number; name: string }[];
}>();
</script>

<template>
  <div class="flex flex-col m-4 gap-4">
    <p>Selected views</p>
    <ul>
      <li v-for="view in props.views" :key="view.id">
        {{ view.name }}
      </li>
    </ul>
  </div>
</template>