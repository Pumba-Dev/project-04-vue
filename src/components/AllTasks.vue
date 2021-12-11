<template>
  <div class="all-tasks">
    <TaskBoxContainer
      v-for="(task, index) in taskList"
      :key="index"
      :task="task"
      :taskListRemoveFn="taskListRemoveFn"
      :turnTaskCompletedFn="turnTaskCompletedFn"
    />
  </div>
</template>

<script>
import TaskBoxContainer from "./TaskBoxContainer.vue";
export default {
  components: {
    TaskBoxContainer,
  },
  props: {
    taskList: {
      type: Array,
      required: true,
    },
    taskListRemoveFn: {
      type: Function,
      required: true,
    },
    turnTaskCompletedFn: {
      type: Function,
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