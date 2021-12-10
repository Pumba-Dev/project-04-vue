<template>
  <div class="all-tasks">
    <TaskBox v-for="(task, index) in taskList" :key="index" :task="task" />
  </div>
</template>

<script>
import TaskBox from "./TaskBox.vue";
export default {
  components: {
    TaskBox,
  },
  props: {
    taskList: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
.all-tasks {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}
</style>