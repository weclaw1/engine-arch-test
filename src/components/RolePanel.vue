<script setup lang="ts">
import RolePanelViewList from '@/components/RolePanelViewList.vue';
import { ref } from 'vue';

const role = ref<string>('');

const emit = defineEmits<{
  selectedViewsChange: [selectedViews: { id: number; name: string }[]]
}>();

const onChange = (selectedViews: { id: number; name: string }[]) => {
  emit('selectedViewsChange', selectedViews);
};

</script>

<template>
  <div class="flex flex-col m-4 gap-4">
    <input type="text" v-model="role" placeholder="Role name" />
    <RolePanelViewList @change="onChange"/>
  </div>
</template>