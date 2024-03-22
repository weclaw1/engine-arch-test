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
  <div class="role-panel">
    <input type="text" v-model="role" />
    <RolePanelViewList @change="onChange"/>
  </div>
</template>