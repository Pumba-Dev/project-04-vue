<template>
  <div class="tasks-container">
    <Component
      :is="chooseTasksComponent()"
      :taskList="taskList"
      :taskListRemoveFn="taskListRemoveFn"
      :turnTaskCompletedFn="turnTaskCompletedFn"
    />
  </div>
</template>

<script>
import AllTasks from "../objects/AllTasks.vue";
import NoTaskMsg from "../objects/NoTaskMsg.vue";
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
    taskListRemoveFn: {
      type: Function,
      required: true,
    },
    turnTaskCompletedFn: {
      type: Function,
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
  width: 75%;
}
</style>