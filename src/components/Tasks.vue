<template>
  <div :key="task.id" v-for="task in tasks">
    <Task_Single
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task_Single from "./Task.vue";
export default {
  name: "Tasks_Main",
  props: {
    tasks: Array,
  },
  components: {
    Task_Single,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
