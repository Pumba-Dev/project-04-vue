<template>
  <div
    class="task-box"
    :class="{ completed: hasCompleted }"
    @click="hasCompleted = !hasCompleted"
  >
    {{ description }}
    <CloseBox @click="removeTask()" />
  </div>
</template>

<script>
import CloseBox from "./CloseBox.vue";
export default {
  components: { CloseBox },
  props: {
    description: {
      type: String,
      required: true,
      default: "Task Default",
    },
    taskListRemoveFn: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      hasCompleted: false,
    };
  },
  methods: {
    removeTask() {
      console.log("ta saindo");
      this.taskListRemoveFn(this.description);
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
  color: rgba(255, 255, 255, 0.5);
  border-radius: 6px;
  box-shadow: inset 6px 0px rgba(0, 0, 0, 0.2);
  user-select: none;
}

.task-box:hover {
  transform: scale(105%);
}

.completed {
  background-color: rgba(0, 255, 0, 0.4);
  text-decoration-line: line-through;
}
</style>