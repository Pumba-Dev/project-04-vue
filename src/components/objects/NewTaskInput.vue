<template>
  <input
    type="text"
    class="new-task-input"
    placeholder="New Task?"
    v-model="taskDescriptionInput"
    v-on:keyup.enter="enterInput()"
    @change="setTaskDescriptionInput()"
  />
</template>

<script>
export default {
  data() {
    return {
      taskDescriptionInput: "",
    };
  },
  methods: {
    enterInput() {
      this.$emit("enterInputByKey", this.taskDescriptionInput);
    },
    setTaskDescriptionInput() {
      this.$emit("NewTaskDescription", this.taskDescriptionInput);
    },
  },
};
</script>

<style>
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
</style>