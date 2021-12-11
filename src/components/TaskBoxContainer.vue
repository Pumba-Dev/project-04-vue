<template>
  <div class="task-box-container">
    <CloseBox @RemoveThisTask="taskListRemoveFn(task.desc)" />
    <TaskBox :task="task" :turnTaskCompletedFn="turnTaskCompletedFn" />
  </div>
</template>

<script>
import CloseBox from "./CloseBox.vue";
import TaskBox from "./TaskBox.vue";
export default {
  components: {
    CloseBox,
    TaskBox,
  },
  props: {
    task: {
      type: Object,
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
  computed: {
    hasCompleted() {
      return this.task.hasCompleted;
    },
  },
  methods: {
    makeTaskComplete() {
      this.turnTaskCompletedFn(this.task.desc);
    },
  },
};
</script>

<style>
.task-box-container {
  position: relative;
}
</style>