<template>
  <div class="tasks-container">
    <component :is="chooseTasksComponent()" :taskList="taskList" />
  </div>
</template>

<script>
import AllTasks from "./AllTasks.vue";
import NoTaskMsg from "./NoTaskMsg.vue";
export default {
  components: {
    AllTasks,
    NoTaskMsg,
  },
  props: {
    taskList: {
      type: Array,
      required: true,
    },
  },
  computed: {
    haveTaskRegistered() {
      return this.taskList.length == 0 ? false : true;
    },
  },
  methods: {
    chooseTasksComponent() {
      return this.haveTaskRegistered ? AllTasks : NoTaskMsg;
    },
  },
};
</script>

<style>
.tasks-container {
  padding-top: 20px;
}
</style>