<template>
  <div class="task-box-container">
    <CloseBox @RemoveThisTask="taskListRemoveFn(task.desc)" />
    <TaskBox :task="task" :turnTaskCompletedFn="turnTaskCompletedFn" />
  </div>
</template>

<script>
import CloseBox from "../objects/CloseBox.vue";
import TaskBox from "../objects/TaskBox.vue";
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