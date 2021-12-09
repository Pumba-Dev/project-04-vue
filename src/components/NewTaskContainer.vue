<template>
  <div class="task-container">
    <new-task-input />
    <new-task-btn />
  </div>
</template>

<script>
import NewTaskBtn from "./NewTaskBtn.vue";
import NewTaskInput from "./NewTaskInput.vue";
export default {
  components: {
    NewTaskInput,
    NewTaskBtn,
  },
};
</script>

<style>
.task-container {
  padding-top: 20px;
  display: flex;
  justify-content: center;
  height: 25px;
}
</style>