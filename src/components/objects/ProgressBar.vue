<template>
  <div class="progress-bar" :style="{ width: taskProgress + '%' }"></div>
</template>

<script>
export default {
  props: {
    taskProgress: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style>
.progress-bar {
  height: 100%;
  background-color: green;
  border-radius: 5px;
}
</style>