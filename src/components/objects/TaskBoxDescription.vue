<template>
  <div class="task-box-description">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style>
.task-box-description {
  position: absolute;
  width: 85%;
  height: 50%;
  bottom: 5px;
  right: 5px;
  text-align: center;
  overflow: hidden;
  font-size: 1.03rem;
}
</style>