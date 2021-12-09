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
  data() {
    return {
      taskProgress: 80,
    };
  },
};
</script>

<style>
.progress-container {
  display: flex;
  align-items: center;
  border: 1px solid white;
  border-radius: 5px;
  width: 70vw;
  height: 20px;
}

.task-progress {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  color: white;
  font-family: cursive;
}
</style>