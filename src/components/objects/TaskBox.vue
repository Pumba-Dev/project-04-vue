<template>
  <div
    class="task-box"
    :class="{ completed: hasCompleted }"
    @click="makeTaskComplete()"
  >
    <TaskBoxDescription>
      <span :style="{ 'text-decoration-line': sublimeTaskIfCompleted }">
        {{ task.desc }}
      </span>
    </TaskBoxDescription>
  </div>
</template>

<script>
import TaskBoxDescription from "./TaskBoxDescription";
export default {
  components: {
    TaskBoxDescription,
  },
  props: {
    task: {
      type: Object,
      required: true,
    },
    turnTaskCompletedFn: {
      type: Function,
      required: true,
    },
  },
  computed: {
    hasCompleted() {
      return this.task.hasCompleted;
    },
    sublimeTaskIfCompleted() {
      if (this.hasCompleted) return "line-through";
      else return "";
    },
  },
  methods: {
    makeTaskComplete() {
      this.turnTaskCompletedFn(this.task.desc);
    },
  },
};
</script>

<style>
.task-box {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 70px;
  width: 165px;
  background-color: rgba(250, 60, 60, 0.9);
  color: rgba(255, 255, 255, 0.8);
  word-break: break-all;
  border-radius: 6px;
  box-shadow: inset 6px 0px rgba(0, 0, 0, 0.2);
}

.completed {
  background-color: rgba(0, 255, 0, 0.4);
}
</style>