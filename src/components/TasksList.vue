<script setup>
import Task from './Task.vue';

const { tasks } = defineProps({
  tasks: Array,
});
const emit = defineEmits(['delete-task', 'toggle-reminder']);
</script>

<template>
  <ul class="tasks">
    <p v-if="!tasks.length">No tasks to show</p>
    <!-- <div :key="task.id" v-else v-for="task in tasks"> -->
    <Task
      :key="task.id"
      v-for="task in tasks"
      :task="task"
      @toggle-reminder="emit('toggle-reminder', $event)"
      @delete-task="emit('delete-task', $event)"
    />
  </ul>
</template>
