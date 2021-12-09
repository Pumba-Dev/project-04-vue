<template>
  <div id="app" class="bg-container">
    <main-container></main-container>
  </div>
</template>

<script>
import MainContainer from "./components/MainContainer.vue";
export default {
  components: { MainContainer },
};
</script>

<style scoped>
.bg-container {
  background: #0f2027;
  background: -webkit-linear-gradient(to right, #2c5364, #203a43, #0f2027);
  background: linear-gradient(to right, #2c5364, #203a43, #0f2027);
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
