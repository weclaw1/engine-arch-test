<script setup lang="ts">
import ViewList from '@/components/ViewList.vue';
import { ref } from 'vue';

const role = ref<string>('');
</script>

<template>
  <div class="role-panel">
    <input type="text" v-model="role" />
    <ViewList />
  </div>
</template>