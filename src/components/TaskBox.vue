<template>
  <div
    class="task-box"
    :class="{ completed: hasCompleted }"
    @click="makeTaskComplete()"
  >
    {{ task.desc }}
  </div>
</template>

<script>
export default {
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
  text-decoration-line: line-through;
}
</style>