<template>
  <div class="main-container">
    <head-title />
    <progress-container :taskList="taskList" />
    <new-task-container :taskListIncludeFn="taskListInclude" />
    <tasks-container
      :taskList="taskList"
      :taskListRemoveFn="taskListRemove"
      :turnTaskCompletedFn="turnTaskCompleted"
    />
  </div>
</template>

<script>
import Task from "./Task";
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
      taskList: [],
    };
  },
  methods: {
    taskListInclude(newTaskDesc) {
      if (newTaskDesc != "") this.taskList.push(new Task(newTaskDesc));
    },
    taskIndexInList(taskDesc) {
      for (let index in this.taskList) {
        if (this.taskList[index].desc == taskDesc) {
          return index;
        }
      }
      return -1;
    },
    taskListRemove(taskDesc) {
      for (let index in this.taskList) {
        if (this.taskList[index].desc == taskDesc) {
          this.taskList.splice(index, 1);
        }
      }
    },
    turnTaskCompleted(taskDesc) {
      const taskIndex = this.taskIndexInList(taskDesc);
      this.taskList[taskIndex].hasCompleted =
        !this.taskList[taskIndex].hasCompleted;
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