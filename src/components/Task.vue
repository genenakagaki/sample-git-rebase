<script setup>
const props = defineProps({
  modelValue: Object,
  taskStatusType: Array
})
</script>

<template>
  <div>
    <select v-model="modelValue.status">
      <option v-for="status in taskStatusType" :key="status">{{ status }}</option>
    </select>
    <label :for="modelValue.name">{{ modelValue.name }}</label>
  </div>
</template>
