<template>
  <div class="main-container">
    <head-title />
    <progress-container />
    <new-task-container />
    <tasks-container
      :taskList="[
        { description: 'Minha Tarefa', hasCompleted: true },
        { description: 'Minha Tarefa 2', hasCompleted: false },
        { description: 'Minha Tarefa 3', hasCompleted: false },
        { description: 'Minha Tarefa 3', hasCompleted: false },
        { description: 'Minha Tarefa 3', hasCompleted: true },
        { description: 'Minha Tarefa 3', hasCompleted: false },
        { description: 'Minha Tarefa 3', hasCompleted: false },
        { description: 'Minha Tarefa 3', hasCompleted: false },
      ]"
    />
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
      taskList: [],
    };
  },
  methods: {
    taskListInclude(newTask) {
      this.taskList << newTask;
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