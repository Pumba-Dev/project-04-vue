<template>
  <div class="progress-container">
    <span class="task-progress"> {{ taskProgress }}% </span>
    <progress-bar :taskProgress="taskProgress"></progress-bar>
  </div>
</template>

<script>
import ProgressBar from "./ProgressBar.vue";
export default {
  components: {
    ProgressBar,
  },
  props: {
    taskList: {
      type: Array,
      required: true,
    },
  },
  computed: {
    taskProgress() {
      const totalOfTasks = this.taskList.length;
      if (totalOfTasks == 0) return 0;
      let totalOfCompletedTasks = 0;
      for (let index in this.taskList) {
        if (this.taskList[index].hasCompleted) {
          totalOfCompletedTasks++;
        }
      }
      const taskProgress = Math.floor(
        (totalOfCompletedTasks / totalOfTasks) * 100
      );
      return taskProgress;
    },
  },
};
</script>

<style>
.progress-container {
  display: flex;
  align-items: center;
  border: 1px solid white;
  border-radius: 5px;
  width: 65vw;
  height: 20px;
  user-select: none;
}

.task-progress {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  color: white;
  font-family: sans-serif;
}
</style>