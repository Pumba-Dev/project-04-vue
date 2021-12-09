<template>
  <div class="main-container">
    <head-title />
    <progress-container />
    <new-task-container />
    <tasks-container :tasksList="[]" />
  </div>
</template>

<script>
import HeadTitle from "./HeadTitle.vue";
import ProgressContainer from "./ProgressContainer.vue";
import NewTaskContainer from "./NewTaskContainer.vue";
import TasksContainer from "./TasksContainer.vue";
export default {
  components: {
    HeadTitle,
    ProgressContainer,
    NewTaskContainer,
    TasksContainer,
  },
};
</script>

<style>
.main-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>