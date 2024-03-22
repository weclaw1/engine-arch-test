<script setup lang="ts">
import RolePanel from '@/components/RolePanel.vue';
import RoleViewsList from '@/components/RoleViewsList.vue';
import { ref } from 'vue';

const views = ref<{ id: number; name: string }[]>([]);
const onSelectedViewsChange = (selectedViews: { id: number; name: string }[]) => {
  views.value = selectedViews;
};
</script>

<template>
  <main>
    <div class="flex flex-row">
      <RolePanel @selected-views-change="onSelectedViewsChange"/>
      <RoleViewsList :views="views"/>
    </div>
  </main>
</template>
