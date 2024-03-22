<script setup lang="ts">
const props = defineProps<{
  views: { id: number; name: string }[];
}>();
</script>

<template>
  <div class="role-views-list">
    <p>Selected views</p>
    <ul>
      <li v-for="view in props.views" :key="view.id">
        {{ view.name }}
      </li>
    </ul>
  </div>
</template>