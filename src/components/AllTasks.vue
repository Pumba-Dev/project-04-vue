<template>
  <div class="all-tasks">
    <TaskBox
      v-for="(task, index) in taskList"
      :key="index"
      :task="task"
      :taskListRemoveFn="taskListRemoveFn"
      :turnTaskCompletedFn="turnTaskCompletedFn"
    />
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