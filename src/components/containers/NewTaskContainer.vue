<template>
  <div class="task-container">
    <NewTaskInput
      @enterInputByKey="enterInput()"
      @NewTaskDescription="NewTaskDescription($event)"
    />
    <NewTaskBtn @enterInputByBtn="enterInput()" />
  </div>
</template>

<script>
import NewTaskInput from "../objects/NewTaskInput.vue";
import NewTaskBtn from "../objects/NewTaskBtn.vue";
export default {
  components: {
    NewTaskInput,
    NewTaskBtn,
  },
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
  methods: {
    enterInput() {
      this.taskListIncludeFn(this.taskDescriptionInput);
      this.taskDescriptionInput = "";
    },
    NewTaskDescription(taskDesc) {
      this.taskDescriptionInput = taskDesc;
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
</style>