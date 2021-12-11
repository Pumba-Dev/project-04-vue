<template>
  <div class="close-box" @click="removeTask()">X</div>
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

<style scoped>
.close-box {
  background-color: rgba(255, 255, 255, 0.6);
  color: rgb(0, 0, 0, 0.4);
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
}

.close-box:hover {
  background-color: rgba(255, 255, 255, 0.8);
  color: rgb(0, 0, 0, 0.6);
  cursor: pointer;
}
</style>