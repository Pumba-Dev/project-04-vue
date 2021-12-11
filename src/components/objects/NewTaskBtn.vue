<template>
  <div class="new-task-btn" @click="enterInput()">+</div>
</template>

<script>
export default {
  methods: {
    enterInput() {
      this.$emit("enterInputByBtn");
    },
  },
};
</script>

<style>
.new-task-btn {
  background-color: rgba(0, 140, 255, 0.822);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 0px 5px 5px 0px;
  width: 5vh;
  min-width: max-content;
  height: 100%;
  padding: 1px;
  color: white;
  font-size: 1.2rem;
  font-family: Arial;
  display: flex;
  align-items: center;
  justify-content: center;
  user-select: none;
}
</style>