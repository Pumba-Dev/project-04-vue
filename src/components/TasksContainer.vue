<template>
  <div class="tasks-container">
    <component :is="chooseTasksComponent()" />
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
    tasksList: {
      type: Array,
      required: true,
    },
  },
  computed: {
    haveTaskRegistered() {
      return this.tasksList.length == 0 ? false : true;
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