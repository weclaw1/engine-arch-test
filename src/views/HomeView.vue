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
  <div class="w-full max-w-screen-2xl mx-auto py-4 px-4 sm:px-6 md:px-8 min-h-[calc(100vh-4.5rem)]">
    <div class="w-full flex flex-row">
      <div class="flex-1 basis-1/4">
        <RolePanel @selected-views-change="onSelectedViewsChange"/>
      </div>
      <div class="flex-1 basis-3/4">
        <RoleViewsList :views="views"/>
      </div>
    </div>
  </div>
</template>
