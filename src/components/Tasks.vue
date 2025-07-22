<script>
import Task from './Task.vue';
export default {
  name: 'Tasks',
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ['delete-task', 'toggle-reminder'],
};
</script>

<template>
  <div class="tasks" v-if="!tasks.length">
    <p>No tasks to show</p>
  </div>
  <div :key="task.id" v-else v-for="task in tasks">
    <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
  </div>
</template>
