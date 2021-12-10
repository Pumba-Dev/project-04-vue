<template>
  <div class="task-container">
    <input
      type="text"
      class="new-task-input"
      placeholder="New Task?"
      v-model="taskDescriptionInput"
      v-on:keyup.enter="taskListIncludeFn(taskDescriptionInput)"
    />
    <div class="new-task-btn" @click="taskListIncludeFn(taskDescriptionInput)">
      +
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      taskDescriptionInput: "",
    };
  },
  props: {
    taskListIncludeFn: {
      type: Function,
      required: true,
    },
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

.new-task-input {
  background-color: rgba(255, 255, 255, 0.1);
  width: 30vh;
  height: 100%;
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 5px 0px 0px 5px;
  color: white;
}

.new-task-input:focus {
  outline: none;
}

.new-task-btn {
  background-color: rgba(0, 140, 255, 0.822);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 0px 5px 5px 0px;
  width: 5vh;
  min-width: max-content;
  height: 100%;
  padding: 1px;
  color: white;
  font-size: 1.2rem;
  font-family: Arial;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>