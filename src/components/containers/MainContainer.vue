<template>
  <div class="main-container">
    <HeadTitle />
    <ProgressContainer :taskList="taskList" />
    <NewTaskContainer :taskListIncludeFn="taskListInclude" />
    <AllTasksContainer
      :taskList="taskList"
      :taskListRemoveFn="taskListRemove"
      :turnTaskCompletedFn="turnTaskCompleted"
    />
  </div>
</template>

<script>
import Task from "../../class/Task";
import HeadTitle from "../objects/HeadTitle.vue";
import ProgressContainer from "../containers/ProgressContainer.vue";
import NewTaskContainer from "../containers/NewTaskContainer.vue";
import AllTasksContainer from "./AllTasksContainer.vue";
export default {
  components: {
    HeadTitle,
    ProgressContainer,
    NewTaskContainer,
    AllTasksContainer,
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
      const taskIndex = this.taskIndexInList(taskDesc);
      this.taskList.splice(taskIndex, 1);
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