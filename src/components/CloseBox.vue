<template>
  <div class="close-box" @click="removeTask()">x</div>
</template>

<script>
export default {
  methods: {
    removeTask() {
      this.$emit("RemoveThisTask");
    },
  },
};
</script>

<style>
.close-box {
  background-color: rgba(255, 255, 255, 0.5);
  color: black;
  font-family: Monospace;
  font-size: 1rem;
  min-width: 20px;
  min-height: 20px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  right: 5px;
  top: 5px;
  user-select: none;
}

.close-box:hover {
  background-color: rgba(255, 255, 255, 0.8);
  cursor: pointer;
}
</style>