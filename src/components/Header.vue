<template>
  <header>
    <h1>{{ title }}</h1>
    <Button_Task
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<script>
import Button_Task from "./Button";
export default {
  name: "Header_Main",
  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {
    Button_Task,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}
</style>
