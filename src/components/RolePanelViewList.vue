<script setup lang="ts">
import { computed, ref } from 'vue';

const views = ref([
  { id: 1, name: 'Dispatcher Screen' },
  { id: 2, name: 'Shifts Manager' },
  { id: 3, name: 'Live Panel' },
  { id: 4, name: 'Client Communication Messages' },
]);

const search = ref('');
const filteredViews = computed(() => {
  return views.value.filter((view) => view.name.toLowerCase().includes(search.value.toLowerCase()));
});

const selectedViews = ref<{ id: number; name: string }[]>([]);

const emit = defineEmits<{
  change: [selectedViews: { id: number; name: string }[]]
}>();

const onChange = () => {
  emit('change', selectedViews.value);
};
</script>
<template>
  <input type="text" v-model="search" placeholder="Search" />
  <p>Select views to add to that role</p>
  <ul>
    <li v-for="view in filteredViews" :key="view.id">
      <input type="checkbox" v-model="selectedViews" :value="view" @change="onChange" />
      {{ view.name }}
    </li>
  </ul>
</template>