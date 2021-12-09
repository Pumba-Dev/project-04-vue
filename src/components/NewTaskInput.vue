<template>
  <input type="text" placeholder="New Task?" class="new-task-input" />
</template>

<script>
export default {};
</script>

<style>
.new-task-input {
  background-color: rgba(255, 255, 255, 0.1);
  width: 30vh;
  height: 100%;
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 5px 0px 0px 5px;
  color: white;
}

.new-task-input:focus {
  outline: none;
}
</style>