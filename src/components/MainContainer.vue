<template>
  <div class="main-container">
    <head-title />
    <progress-container />
    <new-task-container :taskListIncludeFn="taskListInclude" />
    <tasks-container :taskList="taskList" :taskListRemoveFn="taskListRemove" />
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
  data() {
    return {
      taskList: ["testando"],
    };
  },
  methods: {
    taskListInclude(newTask) {
      if (newTask != "") this.taskList.push(newTask);
    },
    taskListRemove(taskDesc) {
      let index = 0;
      for (let task in this.taskList) {
        if (task == taskDesc) {
          this.taskList.splice(index, 1);
        }
        index++;
      }
    },
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