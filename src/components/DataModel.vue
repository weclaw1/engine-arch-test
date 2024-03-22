<script setup lang="ts">
const props = defineProps<{
  id: number;
  name: string;
}>();
</script>
<template>
  <table class="table table-fixed">
    <thead>
      <tr>
        <th>Data Model</th>
        <th>Available Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>{{ props.name }}</td>
        <td>
          <div class="flex flex-col gap-2">
            <button class="btn">update</button>
            <button class="btn">remove</button>
            <button class="btn">create</button>
          </div>
        </td>
      </tr>
    </tbody>
  </table>
</template>